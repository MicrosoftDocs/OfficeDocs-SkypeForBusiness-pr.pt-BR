---
title: Atualizar AAD conectar para incluir mais de uma floresta
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apêndice inclui as etapas detalhadas para a atualização AAD conectar para incluir mais de uma floresta como parte da consolidação de nuvem para equipes e Skype para negócios.
ms.openlocfilehash: d7229d54c159f7e07a233636f1576830e667dce5
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247603"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="8fa08-103">Atualizar AAD conectar para incluir mais de uma floresta</span><span class="sxs-lookup"><span data-stu-id="8fa08-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="8fa08-104">Conectar do Azure AD oferecer suporte à [sincronização de várias florestas](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span><span class="sxs-lookup"><span data-stu-id="8fa08-104">Azure AD Connect supports [syncing from multiple forests](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="8fa08-105">No entanto, ele oferece suporte a apenas uma instância do Azure Connect da AD está sincronizando para AAD.</span><span class="sxs-lookup"><span data-stu-id="8fa08-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="8fa08-106">Portanto, em casos onde o Azure AD já estiver instalado em uma floresta, a instância existente do AAD conectar deve ser atualizada para a floresta adicional da sincronização.</span><span class="sxs-lookup"><span data-stu-id="8fa08-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="8fa08-107">Se todas as identidades são representadas somente uma vez entre as duas florestas (ou seja, se você ainda não tiver feito todos os contatos habilitados para email), e em seguida, você pode simplesmente execute novamente o assistente AAD conectar, escolha "Personalizar opções de sincronização" e, em seguida, no \*\*conectar seus diretórios \*\*página, insira o nome da floresta adicional e credenciais.</span><span class="sxs-lookup"><span data-stu-id="8fa08-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="8fa08-108">![Conectar sua página de diretórios](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="8fa08-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="8fa08-109">No entanto, se os usuários podem existir em mais de um diretório e você vai mesclando os dados (por exemplo, se existem objetos de contato em uma floresta que corresponde aos usuários em outra floresta), você precisará desinstalar Connect do Azure AD e instalá-la novamente.</span><span class="sxs-lookup"><span data-stu-id="8fa08-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="8fa08-110">Isso ocorre porque a condição de regras de ingresso entre florestas só pode ser configurada durante a instalação do primeira.</span><span class="sxs-lookup"><span data-stu-id="8fa08-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="8fa08-111">Isso é feito na página a seguir:</span><span class="sxs-lookup"><span data-stu-id="8fa08-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="8fa08-112">![O que identifica unicamente sua página de usuários](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="8fa08-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="8fa08-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8fa08-113">See also</span></span>

[<span data-ttu-id="8fa08-114">Consolidação de nuvem para equipes e Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="8fa08-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)