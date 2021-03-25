---
title: Atualizar o AAD Connect para incluir mais de uma floresta
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apêndice inclui etapas detalhadas para atualizar o AAD Connect para incluir mais de uma floresta como parte da consolidação de nuvem para o Teams e o Skype for Business.
ms.openlocfilehash: 19b761f3b64caf7afad7d37a51ae391e23d6b5ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120370"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="41a49-103">Atualizar o AAD Connect para incluir mais de uma floresta</span><span class="sxs-lookup"><span data-stu-id="41a49-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="41a49-104">O Azure AD Connect dá suporte [à sincronização de várias florestas.](/azure/active-directory/connect/active-directory-aadconnect-topologies)</span><span class="sxs-lookup"><span data-stu-id="41a49-104">Azure AD Connect supports [syncing from multiple forests](/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="41a49-105">No entanto, ele dá suporte a apenas uma instância da sincronização do Azure AD Connect com o AAD.</span><span class="sxs-lookup"><span data-stu-id="41a49-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="41a49-106">Portanto, nos casos em que o Azure AD já está instalado em uma floresta, a instância existente do AAD Connect deve ser atualizada para sincronizar a partir da floresta adicional.</span><span class="sxs-lookup"><span data-stu-id="41a49-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="41a49-107">Se todas as identidades são representadas apenas uma vez em ambas as florestas (ou seja, você não fez nenhum contato habilitado para email), então você pode simplesmente executar novamente o assistente do AAD Connect, escolha "Personalizar opções de sincronização", e, em seguida, na página **Conectar** Seus Diretórios, insira o nome da floresta adicional e os créditos.</span><span class="sxs-lookup"><span data-stu-id="41a49-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="41a49-108">![A página Conectar seus diretórios](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="41a49-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="41a49-109">No entanto, se os usuários puderem existir em mais de um diretório e você estiver mesclando os dados (por exemplo, se os objetos de contato existirem em uma floresta correspondente aos usuários em outra floresta), você precisará desinstalar o Azure AD Connect e instalá-los novamente.</span><span class="sxs-lookup"><span data-stu-id="41a49-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="41a49-110">Isso porque a condição de regras de junção entre florestas só pode ser configurada durante a primeira instalação.</span><span class="sxs-lookup"><span data-stu-id="41a49-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="41a49-111">Isso é feito na página a seguir:</span><span class="sxs-lookup"><span data-stu-id="41a49-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="41a49-112">![A página Identificando seus usuários com exclusividade](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="41a49-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="41a49-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="41a49-113">See also</span></span>

[<span data-ttu-id="41a49-114">Consolidação de nuvem para Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="41a49-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)