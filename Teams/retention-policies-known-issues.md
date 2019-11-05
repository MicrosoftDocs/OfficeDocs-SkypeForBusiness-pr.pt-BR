---
title: Problemas conhecidos com políticas de retenção no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anach
description: Lista atual de problemas conhecidos para políticas de retenção do Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5565409ea2f3dbb83754ced08a78e12283b1601c
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968332"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="dfa29-103">Problemas conhecidos com políticas de retenção no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dfa29-103">Known issues for retention policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="dfa29-104">Ainda não damos suporte à configuração para a retenção de mensagens de canal privado.</span><span class="sxs-lookup"><span data-stu-id="dfa29-104">We don’t yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="dfa29-105">A retenção de arquivos compartilhados em canais privados tem suporte.</span><span class="sxs-lookup"><span data-stu-id="dfa29-105">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="dfa29-106">Veja a seguir problemas conhecidos de políticas de retenção no Teams que estão sendo controladas e investigadas.</span><span class="sxs-lookup"><span data-stu-id="dfa29-106">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="dfa29-107">Em escolher equipes na linha de localização de mensagens de canal do Teams, você pode ver os grupos do Office 365 que não são equipes também.</span><span class="sxs-lookup"><span data-stu-id="dfa29-107">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="dfa29-108">Isso será abordado no futuro.</span><span class="sxs-lookup"><span data-stu-id="dfa29-108">This will be addressed in the future.</span></span>

- <span data-ttu-id="dfa29-109">Em escolher usuários na linha de local do chat do Teams, você pode ver convidados e usuários que não são usuários da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="dfa29-109">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="dfa29-110">As políticas de retenção não devem ser definidas para convidados e estamos trabalhando para removê-las da lista.</span><span class="sxs-lookup"><span data-stu-id="dfa29-110">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="dfa29-111">O assistente de ciclo de vida do Exchange (ELC) é executado diariamente, mas tem um SLA de 7 dias.</span><span class="sxs-lookup"><span data-stu-id="dfa29-111">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="dfa29-112">Como resultado, é possível que, se você tiver uma política de retenção do teams para excluir itens com mais de 60 dias, esses itens possam persistir por até 67 dias.</span><span class="sxs-lookup"><span data-stu-id="dfa29-112">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="dfa29-113">Essa não é uma nova situação-ela segue o modelo do Exchange.</span><span class="sxs-lookup"><span data-stu-id="dfa29-113">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="dfa29-114">É claro que, na maioria dos casos, não há atraso.</span><span class="sxs-lookup"><span data-stu-id="dfa29-114">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![Um ícone representando um ponto de decisão](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="dfa29-116">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="dfa29-116">Decision point</span></span>         |<span data-ttu-id="dfa29-117">Quais são os recursos de segurança e conformidade exigidos pela sua organização?</span><span class="sxs-lookup"><span data-stu-id="dfa29-117">What security and compliance features does your organization require?</span></span> <span data-ttu-id="dfa29-118">A sua organização tem as licenças necessárias para atender aos requisitos empresariais de segurança e conformidade?</span><span class="sxs-lookup"><span data-stu-id="dfa29-118">Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![Um ícone que representa as próximas etapas](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="dfa29-120">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="dfa29-120">Next steps</span></span>         |<span data-ttu-id="dfa29-121">Documente seus recursos obrigatórios de segurança e conformidade.</span><span class="sxs-lookup"><span data-stu-id="dfa29-121">Document your required security and compliance features.</span></span>         |
