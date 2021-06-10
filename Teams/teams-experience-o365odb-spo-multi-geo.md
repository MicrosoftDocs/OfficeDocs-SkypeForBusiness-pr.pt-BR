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
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="239b4-103">Teams experiência em uma Microsoft 365 multi-geo-habilitada para vários ambientes</span><span class="sxs-lookup"><span data-stu-id="239b4-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="239b4-104">Microsoft Teams é o software de chat em grupo, o hub para o trabalho em equipe Microsoft 365 e Office 365.</span><span class="sxs-lookup"><span data-stu-id="239b4-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="239b4-105">Ele é alimentado pelo serviço Microsoft 365 Grupos, juntamente com o SharePoint Online e OneDrive for Business para sua experiência de arquivos.</span><span class="sxs-lookup"><span data-stu-id="239b4-105">It's powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="239b4-106">Em uma locação de OneDrive for Business/SharePoint Online com Multi-Geo, na qual o locatário é estendido para muitos locais geográficos, como América do Norte, Europa e Austrália, a experiência de arquivos subjacentes é multi-geo-ciente, portanto, Teams experiência com colaboração de arquivos também é multi-geo-ciente.</span><span class="sxs-lookup"><span data-stu-id="239b4-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo-aware, so the Teams experience with file collaboration is also Multi-Geo-aware.</span></span> <span data-ttu-id="239b4-107">Essa funcionalidade é um recurso de ponta-chave para Teams arquivos de superfície hospedados em vários Geos em sua experiência de arquivos nativos.</span><span class="sxs-lookup"><span data-stu-id="239b4-107">This functionality is a key leading-edge capability for Teams to surface files that are hosted across multiple Geos in its native files experience.</span></span> <span data-ttu-id="239b4-108">Isso também inclui arquivos OneNote e Wiki.</span><span class="sxs-lookup"><span data-stu-id="239b4-108">This also includes OneNote and Wiki files.</span></span>

<span data-ttu-id="239b4-109">Por exemplo, em uma locação da Contoso com a Europa como satélite Geo e América do Norte como  o Geo central, um usuário de satélite europeu verá seus arquivos de OneDrive na guia Arquivos no painel esquerdo, embora os arquivos sejam hospedados no local de dados da Europa e os Estados Unidos sejam o local central do locatário.</span><span class="sxs-lookup"><span data-stu-id="239b4-109">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see their OneDrive files under the **Files** tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="239b4-110">Além disso, o usuário pode acessar os arquivos usados mais recentemente na **folha de exibição** Recente.</span><span class="sxs-lookup"><span data-stu-id="239b4-110">Also, the user can access the most recently used files under the **Recent** view blade.</span></span> <span data-ttu-id="239b4-111">Arquivos recentes podem incluir arquivos compartilhados de usuários em outras localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="239b4-111">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="239b4-112">Um determinado site de SharePoint equipe também é multi-geo-ciente.</span><span class="sxs-lookup"><span data-stu-id="239b4-112">A given Team’s SharePoint site is also Multi-Geo-aware.</span></span> <span data-ttu-id="239b4-113">Ou seja, se um usuário de satélite europeu estiver criando uma Equipe, o site de SharePoint correspondente será criado no local da Europa.</span><span class="sxs-lookup"><span data-stu-id="239b4-113">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location.</span></span> <span data-ttu-id="239b4-114">Os arquivos associados a essa Equipe serão mantidos em repouso nesse local.</span><span class="sxs-lookup"><span data-stu-id="239b4-114">The files that are associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="239b4-115">Quaisquer experiências subsequentes, como carregar um novo arquivo ou editar o arquivo, serão armazenadas nesse local europeu, mantendo a promessa de residência de dados para esses arquivos.</span><span class="sxs-lookup"><span data-stu-id="239b4-115">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="239b4-116">Como uma locação Multi-Geo é um único locatário global, durante @ menciona que os usuários de satélite poderão ver seus colegas de todo o mundo, independentemente de onde estão.</span><span class="sxs-lookup"><span data-stu-id="239b4-116">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they are.</span></span>

<span data-ttu-id="239b4-117">Conversas em chats, mensagens de canais e anotações/chats de IM de reunião dentro da experiência Teams não têm conhecimento multi-geo e são mantidas somente no local central do locatário.</span><span class="sxs-lookup"><span data-stu-id="239b4-117">Conversations in chats, channels messages, and meeting IM notes/chats within the Teams experience aren't Multi-Geo-aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="239b4-118">Normalmente, as conversas de chat não são aplicadas às necessidades de residência de dados.</span><span class="sxs-lookup"><span data-stu-id="239b4-118">Typically, chat conversations aren’t applied to data residency needs.</span></span> <span data-ttu-id="239b4-119">Para obter mais informações, [consulte Local dos dados em Microsoft Teams](location-of-data-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="239b4-119">For more information, see [Location of data in Microsoft Teams](location-of-data-in-teams.md).</span></span>

<span data-ttu-id="239b4-120">O suporte multi-geo para Teams está [no mapa Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783).</span><span class="sxs-lookup"><span data-stu-id="239b4-120">Multi-Geo support for Teams is on the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783).</span></span>

<span data-ttu-id="239b4-121">Para obter mais informações sobre Multi-Geo, consulte a página Recursos [Multi-Geo da Microsoft](https://aka.ms/multi-geo).</span><span class="sxs-lookup"><span data-stu-id="239b4-121">For more info about Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>
