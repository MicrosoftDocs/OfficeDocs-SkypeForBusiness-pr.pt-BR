---
title: Experiência do teams em uma locação do Microsoft 365 ou do Office 365 do OneDrive e do SharePoint Online habilitado para várias regiões
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: Saiba como usar o Microsoft Teams em uma locação do Microsoft 365 ou do Office 365 do OneDrive e do SharePoint Online com várias regiões habilitada para várias regiões.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 534155d49cda89291e5d8bdfb8da9b8caf0efb5f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780390"
---
<a name="teams-experience-in-a-microsoft-365-or-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a><span data-ttu-id="59125-103">Experiência do teams em uma locação do Microsoft 365 ou do Office 365 do OneDrive e do SharePoint Online habilitado para várias regiões</span><span class="sxs-lookup"><span data-stu-id="59125-103">Teams experience in a Microsoft 365 or Office 365 OneDrive and SharePoint Online Multi-Geo-enabled tenancy</span></span>
===========================================

<span data-ttu-id="59125-104">O Microsoft Teams é um software de chat em grupo, o Hub de trabalho em equipe do Office 365.</span><span class="sxs-lookup"><span data-stu-id="59125-104">Microsoft Teams is group chat software, the hub for teamwork in Office 365.</span></span> <span data-ttu-id="59125-105">Ele é oferecido pelo serviço Microsoft 365 groups juntamente com o SharePoint Online e o OneDrive for Business para a experiência de seus arquivos.</span><span class="sxs-lookup"><span data-stu-id="59125-105">It is powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="59125-106">Em uma locação de várias regiões do OneDrive for Business/SharePoint Online, na qual o locatário é estendido para muitos locais geográficos, como América do Norte, Europa e Austrália, a experiência de arquivos subjacentes é compatível com várias regiões, portanto, a experiência das equipes com colaboração de arquivos também é compatível com várias regiões.</span><span class="sxs-lookup"><span data-stu-id="59125-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo aware, so the Teams experience with file collaboration is also Multi-Geo aware.</span></span> <span data-ttu-id="59125-107">Esta é uma importante funcionalidade de ponta para o uso de arquivos de superfície hospedados em vários GEOS em sua experiência nativa de arquivos.</span><span class="sxs-lookup"><span data-stu-id="59125-107">This is a key leading-edge capability for Teams to surface files hosted across multiple Geos in its native files experience.</span></span>

<span data-ttu-id="59125-108">Por exemplo, em um aluguel da contoso com Europa como uma região satélite e uma América do Norte como a Geo central, um usuário de satélite Europeu verá os arquivos do OneDrive na guia arquivos no painel esquerdo, embora os arquivos estejam hospedados no local de dados da Europa e os Estados Unidos seja o local central do locatário.</span><span class="sxs-lookup"><span data-stu-id="59125-108">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see his or her OneDrive files under the Files tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="59125-109">Além disso, o usuário pode acessar os arquivos usados mais recentemente sob a lâmina de exibição recente.</span><span class="sxs-lookup"><span data-stu-id="59125-109">Also, the user can access the most recently used files under the Recent view blade.</span></span> <span data-ttu-id="59125-110">Os arquivos recentes podem incluir arquivos compartilhados com o usuário de usuários em outras GEOS e podem ser mestres em outros locais geográficos nos quais o locatário é estendido.</span><span class="sxs-lookup"><span data-stu-id="59125-110">Recent files may include files shared with the user from users in other Geos and might be mastered in other Geo locations that the tenant is extended to.</span></span> 

<span data-ttu-id="59125-111">Um site de grupo específico da equipe também reconhece várias regiões.</span><span class="sxs-lookup"><span data-stu-id="59125-111">A given Team’s group site is also Multi-Geo aware.</span></span> <span data-ttu-id="59125-112">Ou seja, se um usuário de satélite europeu estiver criando uma equipe, o site de grupos correspondentes será criado no local da Europa e os arquivos associados a esse grupo serão mantidos em repouso nesse local.</span><span class="sxs-lookup"><span data-stu-id="59125-112">That is, if a European satellite user is creating a Team, the corresponding Groups site will be created in the Europe location and the files associated with that Team group will be kept at rest in that location.</span></span> <span data-ttu-id="59125-113">Quaisquer experiências subsequentes, como carregar um novo arquivo ou editar o arquivo, serão direcionadas para esse local europeu, mantendo a promessa de residência de dados para esses arquivos.</span><span class="sxs-lookup"><span data-stu-id="59125-113">Any subsequent experiences, such as uploading a new file or editing the file, will be targeted to that European location, keeping the promise of data residency for those files.</span></span> <span data-ttu-id="59125-114">Isso é tudo o que se torna possível pelos grupos base do Microsoft 365 tornando o reconhecimento de várias regiões.</span><span class="sxs-lookup"><span data-stu-id="59125-114">This is all made possible by the underlying foundation Microsoft 365 Groups becoming Multi-Geo aware.</span></span>

<span data-ttu-id="59125-115">Como uma locação de várias regiões é um único locatário global, durante a @ menção, os usuários de satélite poderão ver seus colegas em todo o mundo, onde quer que eles estejam.</span><span class="sxs-lookup"><span data-stu-id="59125-115">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they reside.</span></span> 

<span data-ttu-id="59125-116">Observe que as conversas em chats e as anotações de mensagem instantânea da reunião dentro da experiência do usuário não são compatíveis com várias regiões e são mantidas apenas dentro do local central do locatário.</span><span class="sxs-lookup"><span data-stu-id="59125-116">Note that conversations in chats and meeting IM notes within the Teams experience are not Multi-Geo aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="59125-117">Geralmente, as conversas de chat não são aplicadas às necessidades de residência de dados.</span><span class="sxs-lookup"><span data-stu-id="59125-117">Typically, chat conversations aren’t applied to data residency needs.</span></span>

<span data-ttu-id="59125-118">Para obter mais informações sobre o Office 365 multi-Geo, consulte a [página recursos de várias GEOS da Microsoft](https://aka.ms/multi-geo).</span><span class="sxs-lookup"><span data-stu-id="59125-118">For more information about Office 365 Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>