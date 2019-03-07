---
title: Problemas conhecidos para políticas de retenção no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Lista atual de problemas conhecidos para políticas de retenção Teams da Microsoft.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 411ef4bf12d55af0b913443219a00f3f56c7eba2
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461184"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="d03c6-103">Problemas conhecidos para políticas de retenção no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d03c6-103">Known issues for retention policies in Microsoft Teams</span></span>

<span data-ttu-id="d03c6-104">Os seguintes problemas conhecidos para políticas de retenção em equipes que estão sendo rastreados e investigados.</span><span class="sxs-lookup"><span data-stu-id="d03c6-104">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="d03c6-105">Em Escolha equipes na linha local de mensagens do canal de equipes, talvez você veja os grupos do Office 365 que são não também às equipes.</span><span class="sxs-lookup"><span data-stu-id="d03c6-105">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="d03c6-106">Isto será abordado no futuro.</span><span class="sxs-lookup"><span data-stu-id="d03c6-106">This will be addressed in the future.</span></span>

- <span data-ttu-id="d03c6-107">Em Escolha usuários na linha local equipes de bate-papo, talvez você veja convidados e os usuários não-mailbox.</span><span class="sxs-lookup"><span data-stu-id="d03c6-107">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="d03c6-108">Políticas de retenção não devem ser definidos para convidados e estamos trabalhando para removê-los da lista.</span><span class="sxs-lookup"><span data-stu-id="d03c6-108">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="d03c6-109">Assistente de ciclo de vida do Exchange (ELC) executado diariamente, mas ele tem um SLA de 7 dias.</span><span class="sxs-lookup"><span data-stu-id="d03c6-109">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="d03c6-110">Como resultado, é possível que, se você tiver uma política de retenção de equipes para excluir itens mais antigos do que 60 dias, esses itens poderiam persistem até 67 dias.</span><span class="sxs-lookup"><span data-stu-id="d03c6-110">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="d03c6-111">Isso não é uma nova situação - vier o modelo do Exchange.</span><span class="sxs-lookup"><span data-stu-id="d03c6-111">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="d03c6-112">Obviamente, na maioria dos casos, não há nenhum atraso.</span><span class="sxs-lookup"><span data-stu-id="d03c6-112">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="d03c6-114">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="d03c6-114">Decision point</span></span>         |<span data-ttu-id="d03c6-115">Quais são os recursos de segurança e conformidade exigidos pela sua organização?</span><span class="sxs-lookup"><span data-stu-id="d03c6-115">What security and compliance features does your organization require?</span></span> <span data-ttu-id="d03c6-116">A sua organização tem as licenças necessárias para atender aos requisitos empresariais de segurança e conformidade?</span><span class="sxs-lookup"><span data-stu-id="d03c6-116">Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![Ícone de próximos passos.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="d03c6-118">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="d03c6-118">Next steps</span></span>         |<span data-ttu-id="d03c6-119">Documente seus recursos de segurança e conformidade necessários.</span><span class="sxs-lookup"><span data-stu-id="d03c6-119">Document your required security and compliance features.</span></span>         |
