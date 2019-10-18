---
title: Executar um relatório para exibir o uso ativo do StaffHub
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como executar um relatório para obter uma lista de usuários ativos do StaffHub em sua organização.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 49091f7d8ada565adea61bf8219c6da828358893
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569658"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="24339-103">Executar um relatório para exibir o uso ativo do StaffHub</span><span class="sxs-lookup"><span data-stu-id="24339-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="24339-104">A partir de 31 de dezembro de 2019, o Microsoft StaffHub será desativado.</span><span class="sxs-lookup"><span data-stu-id="24339-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="24339-105">Estamos criando recursos de StaffHub no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="24339-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="24339-106">Hoje, o Teams inclui o aplicativo turnos para gerenciamento de agendamento e recursos adicionais se acumularão ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="24339-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="24339-107">O StaffHub deixará de funcionar para todos os usuários em 31 de dezembro de 2019.</span><span class="sxs-lookup"><span data-stu-id="24339-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="24339-108">Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-o para o download do teams.</span><span class="sxs-lookup"><span data-stu-id="24339-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="24339-109">Para saber mais, confira [Microsoft StaffHub para ser desativado](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="24339-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="24339-110">Use as etapas neste artigo para executar um relatório para obter uma lista de usuários ativos do StaffHub em sua organização.</span><span class="sxs-lookup"><span data-stu-id="24339-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="24339-111">Essas informações podem ser úteis quando você se prepara para [mover suas equipes do StaffHub para o Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="24339-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="24339-112">No relatório, você saberá quem precisa incluir em suas comunicações quando fizer a mudança do StaffHub para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="24339-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="24339-113">Você precisa ter o Azure AD Premium para executar as etapas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="24339-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="24339-114">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="24339-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="24339-115">No painel esquerdo, clique no recurso **do Azure Active Directory** .</span><span class="sxs-lookup"><span data-stu-id="24339-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="24339-116">Em **monitoramento**, clique em **entradas**.</span><span class="sxs-lookup"><span data-stu-id="24339-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="24339-117">Em **aplicativo**, digite **Microsoft StaffHub**.</span><span class="sxs-lookup"><span data-stu-id="24339-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="24339-118">Defina o intervalo de datas que você deseja para o relatório e clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="24339-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![Captura de tela mostrando as etapas de como mostrar o uso ativo StaffHub](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="24339-120">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="24339-120">Related topics</span></span>

- [<span data-ttu-id="24339-121">Mover suas equipes do Microsoft StaffHub para turnos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="24339-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
