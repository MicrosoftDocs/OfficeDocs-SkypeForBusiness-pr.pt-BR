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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apêndice inclui etapas detalhadas para atualizar o AAD Connect para incluir mais de uma floresta como parte da consolidação de nuvem para o Teams e o Skype for Business.
ms.openlocfilehash: cbb4811d999601524557e7106840a66682565e5f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160383"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="9519e-103">Atualizar o AAD Connect para incluir mais de uma floresta</span><span class="sxs-lookup"><span data-stu-id="9519e-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="9519e-104">O Azure AD Connect oferece suporte à [sincronização de várias florestas](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span><span class="sxs-lookup"><span data-stu-id="9519e-104">Azure AD Connect supports [syncing from multiple forests](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="9519e-105">No entanto, ele suporta apenas uma instância da sincronização do Azure AD Connect para o AAD.</span><span class="sxs-lookup"><span data-stu-id="9519e-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="9519e-106">Portanto, nos casos em que o Azure AD já está instalado em uma floresta, a instância existente do AAD Connect deve ser atualizada para sincronizar a partir da floresta adicional.</span><span class="sxs-lookup"><span data-stu-id="9519e-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="9519e-107">Se todas as identidades forem representadas apenas uma vez em ambas as florestas (ou seja, se você não tiver feito nenhum contato habilitado para email), poderá simplesmente executar novamente o assistente de conexão do AAD, escolher "Personalizar opções de sincronização" e, em seguida, nos \*\*conectar seus diretórios \*\*Insira o nome da floresta adicional e das credenciais.</span><span class="sxs-lookup"><span data-stu-id="9519e-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="9519e-108">![A página conectar seus diretórios](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="9519e-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="9519e-109">No entanto, se os usuários podem existir em mais de um diretório e você estiver mesclando os dados (por exemplo, se houver objetos de contato em uma floresta correspondente aos usuários em outra floresta), será necessário desinstalar o Azure AD Connect e reinstalá-lo.</span><span class="sxs-lookup"><span data-stu-id="9519e-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="9519e-110">Isso ocorre porque a condição de regras de ingresso entre florestas só pode ser configurada durante a primeira instalação.</span><span class="sxs-lookup"><span data-stu-id="9519e-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="9519e-111">Isso é feito na seguinte página:</span><span class="sxs-lookup"><span data-stu-id="9519e-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="9519e-112">![A página exclusivamente identificando os usuários](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="9519e-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="9519e-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="9519e-113">See also</span></span>

[<span data-ttu-id="9519e-114">Consolidação de nuvem para Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9519e-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)