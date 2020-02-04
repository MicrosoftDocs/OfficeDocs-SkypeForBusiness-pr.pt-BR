---
title: Problemas conhecidos dos planos de chamadas
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: 'Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. '
ms.openlocfilehash: 3441969133c8f67b63b620aff25545b89085858f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692306"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="691aa-103">Problemas conhecidos dos planos de chamadas</span><span class="sxs-lookup"><span data-stu-id="691aa-103">Calling Plans known issues</span></span>

<span data-ttu-id="691aa-p101">Os planos de chamada no Office 365 são um novo recurso encontrado no Skype for Business online. Estes são os problemas atuais que estão sendo controlados e ativamente investigados. Eles serão potencialmente resolvidos quando o recurso for atualizado em futuras versões do Office 365 e do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="691aa-p101">Calling Plans in Office 365 are a new feature found in Skype for Business Online. The following are current issues that are being tracked and actively investigated. They will be potentially resolved when the feature is updated in future builds in Office 365 and Skype for Business Online.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="691aa-107">Problemas conhecidos dos planos de chamadas</span><span class="sxs-lookup"><span data-stu-id="691aa-107">Calling Plans known issues</span></span>

|<span data-ttu-id="691aa-108">**Problema conhecido**</span><span class="sxs-lookup"><span data-stu-id="691aa-108">**Known issue**</span></span>|<span data-ttu-id="691aa-109">**Comentários**</span><span class="sxs-lookup"><span data-stu-id="691aa-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="691aa-110">A transição de licenças do Tech Preview para licenças de produção para planos de chamada não atualiza automaticamente a licença.</span><span class="sxs-lookup"><span data-stu-id="691aa-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="691aa-111">Primeiramente, compre suas novas licenças para que estejam prontas para serem atribuídas aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="691aa-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="691aa-112">Remova a licença promocional (visualização técnica) de um usuário e, em seguida, atribua **imediatamente** o novo **plano de chamadas domésticas** e/ou licenças de **plano de chamada domésticas e internacionais** ao usuário.</span><span class="sxs-lookup"><span data-stu-id="691aa-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="691aa-113">Se você estiver removendo e adicionando licenças para vários usuários, é extremamente importante remover as licenças de todos os usuários usando o Windows PowerShell e depois atribuir **IMEDIATAMENTE** as licenças a todos os usuários também usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="691aa-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="691aa-114">Isso garantirá que não haja interrupção no serviço ao manipular grandes volumes de atribuições de licença de usuário.</span><span class="sxs-lookup"><span data-stu-id="691aa-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="691aa-115">Para os scripts de exemplo do PowerShell, consulte [atribuir licenças do Skype for Business e do Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="691aa-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="691aa-116">**Observação:** Se você estiver usando a conectividade PSTN local para usuários híbridos, *só* precisará atribuir uma licença do **sistema telefônico** .</span><span class="sxs-lookup"><span data-stu-id="691aa-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you  *only*  need to assign a **Phone System** license.</span></span> <span data-ttu-id="691aa-117">Você também **não** deve atribuir um plano de chamada de voz.</span><span class="sxs-lookup"><span data-stu-id="691aa-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="691aa-118">No entanto, se você estiver habilitando planos de chamada no Office 365 para usuários que estão no Office 365, você ainda precisará atribuir um **plano de chamadas domésticas** ou uma licença de **plano de chamadas doméstica e internacional** para esses usuários.</span><span class="sxs-lookup"><span data-stu-id="691aa-118">However, if you are enabling Calling Plans in Office 365 for users that are in Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="691aa-119">Consulte [atribuir licenças do Skype for Business e do Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="691aa-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="691aa-120">Se precisar de mais números de telefone, [entre em contato com o suporte para produtos de negócios-ajuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="691aa-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="691aa-121">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="691aa-121">Related topics</span></span>
[<span data-ttu-id="691aa-122">Perguntas comuns sobre a transferência de números de telefone</span><span class="sxs-lookup"><span data-stu-id="691aa-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="691aa-123">Diferentes tipos de números de telefone usados para Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="691aa-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="691aa-124">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="691aa-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="691aa-125">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="691aa-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="691aa-126">[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="691aa-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 