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
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="3606d-103">Experiência do Teams em uma navegação multi-geo habilitada para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3606d-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="3606d-104">O Microsoft Teams é um software de chat em grupo, o hub para trabalho em equipe no Microsoft 365 e no Office 365.</span><span class="sxs-lookup"><span data-stu-id="3606d-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="3606d-105">Ele é desenvolvido pelo serviço Grupos do Microsoft 365 juntamente com o SharePoint Online e o OneDrive for Business para sua experiência de arquivos.</span><span class="sxs-lookup"><span data-stu-id="3606d-105">It's powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="3606d-106">Em uma locação multi-geográfica do OneDrive for Business/SharePoint Online, na qual o locatário é estendido para muitos locais geográficos, como América do Norte, Europa e Austrália, a experiência de arquivos subjacentes é de ciências geográficas multi-geográficas, portanto, a experiência do Teams com colaboração de arquivos também é multi-geográfica.</span><span class="sxs-lookup"><span data-stu-id="3606d-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo-aware, so the Teams experience with file collaboration is also Multi-Geo-aware.</span></span> <span data-ttu-id="3606d-107">Essa funcionalidade é um recurso de ponta-chave para o Teams superfícier arquivos hospedados em vários Geos em sua experiência de arquivos nativos.</span><span class="sxs-lookup"><span data-stu-id="3606d-107">This functionality is a key leading-edge capability for Teams to surface files that are hosted across multiple Geos in its native files experience.</span></span> <span data-ttu-id="3606d-108">Isso também inclui arquivos Do OneNote e Wiki.</span><span class="sxs-lookup"><span data-stu-id="3606d-108">This also includes OneNote and Wiki files.</span></span>

<span data-ttu-id="3606d-109">Por exemplo, em uma locação da Contoso com a Europa como um satélite Geo e América do  Norte como a Geo central, um usuário de satélite europeu verá seus arquivos do OneDrive sob a guia Arquivos no painel esquerdo, embora os arquivos sejam hospedados no local de dados da Europa e os Estados Unidos sejam o local central do locatário.</span><span class="sxs-lookup"><span data-stu-id="3606d-109">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see their OneDrive files under the **Files** tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="3606d-110">Além disso, o usuário pode acessar os arquivos usados mais recentemente sob **a folha de exibição** Recentes.</span><span class="sxs-lookup"><span data-stu-id="3606d-110">Also, the user can access the most recently used files under the **Recent** view blade.</span></span> <span data-ttu-id="3606d-111">Arquivos recentes podem incluir arquivos compartilhados de usuários em outros locais geo.</span><span class="sxs-lookup"><span data-stu-id="3606d-111">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="3606d-112">Um determinado site do SharePoint da equipe também está ciente de vários pontos.</span><span class="sxs-lookup"><span data-stu-id="3606d-112">A given Team’s SharePoint site is also Multi-Geo-aware.</span></span> <span data-ttu-id="3606d-113">Ou seja, se um usuário de satélite europeu estiver criando uma Equipe, o site do SharePoint correspondente será criado no local da Europa.</span><span class="sxs-lookup"><span data-stu-id="3606d-113">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location.</span></span> <span data-ttu-id="3606d-114">Os arquivos associados a essa Equipe serão mantidos em repouso nesse local.</span><span class="sxs-lookup"><span data-stu-id="3606d-114">The files that are associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="3606d-115">Quaisquer experiências subsequentes, como carregar um novo arquivo ou editar o arquivo, serão armazenadas nesse local europeu, mantendo a promessa de residência de dados para esses arquivos.</span><span class="sxs-lookup"><span data-stu-id="3606d-115">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="3606d-116">Como uma locação Multi-Geo é um locatário global único, durante @menções usuários de satélite poderão ver seus colegas de todo o mundo, independentemente de onde eles estão.</span><span class="sxs-lookup"><span data-stu-id="3606d-116">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they are.</span></span>

<span data-ttu-id="3606d-117">As conversas em chats, mensagens de canais e anotações de mensagens de chat de reunião dentro da experiência do Teams não são multi-geográficas e são mantidas somente dentro do local central do locatário.</span><span class="sxs-lookup"><span data-stu-id="3606d-117">Conversations in chats, channels messages, and meeting IM notes/chats within the Teams experience aren't Multi-Geo-aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="3606d-118">Normalmente, as conversas de chat não são aplicadas às necessidades de residência de dados.</span><span class="sxs-lookup"><span data-stu-id="3606d-118">Typically, chat conversations aren’t applied to data residency needs.</span></span> <span data-ttu-id="3606d-119">Para saber mais, confira [a localização dos dados no Microsoft Teams.](location-of-data-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="3606d-119">For more information, see [Location of data in Microsoft Teams](location-of-data-in-teams.md).</span></span>

<span data-ttu-id="3606d-120">Para obter mais informações sobre a Multi-Geo, consulte a página recursos [multi-geo da Microsoft.](https://aka.ms/multi-geo)</span><span class="sxs-lookup"><span data-stu-id="3606d-120">For more info about Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>
