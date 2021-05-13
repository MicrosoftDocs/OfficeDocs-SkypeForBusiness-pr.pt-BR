---
title: Experiência de atualização de aplicativos Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como atualizar aplicativos em Microsoft Teams.
ms.openlocfilehash: b39b831b644b19038b8f4574acf3e5bc5c50d73c
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337818"
---
# <a name="update-apps-in-microsoft-teams"></a><span data-ttu-id="7791f-103">Atualizar aplicativos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7791f-103">Update apps in Microsoft Teams</span></span>

<span data-ttu-id="7791f-104">Na maioria dos casos, depois que os desenvolvedores de aplicativos publicam uma atualização de aplicativo, a nova versão aparece automaticamente para os usuários.</span><span class="sxs-lookup"><span data-stu-id="7791f-104">In most cases, after app developers publish an app update, the new version automatically appears for users.</span></span> <span data-ttu-id="7791f-105">No entanto, há algumas atualizações para o manifesto <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams que</a> exigem que a aceitação do usuário seja concluída:</span><span class="sxs-lookup"><span data-stu-id="7791f-105">However, there are some updates to the <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="7791f-106">Um bot foi adicionado ou removido</span><span class="sxs-lookup"><span data-stu-id="7791f-106">A bot was added or removed</span></span>
* <span data-ttu-id="7791f-107">A propriedade "botId" de um bot existente foi alterada</span><span class="sxs-lookup"><span data-stu-id="7791f-107">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="7791f-108">A propriedade "isNotificationOnly" de um bot existente foi alterada</span><span class="sxs-lookup"><span data-stu-id="7791f-108">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="7791f-109">A propriedade "supportsFiles" do bot foi alterada</span><span class="sxs-lookup"><span data-stu-id="7791f-109">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="7791f-110">Uma extensão de mensagens foi adicionada ou removida</span><span class="sxs-lookup"><span data-stu-id="7791f-110">A messaging extension was added or removed</span></span>
* <span data-ttu-id="7791f-111">Um novo conector foi adicionado</span><span class="sxs-lookup"><span data-stu-id="7791f-111">A new connector was added</span></span>
* <span data-ttu-id="7791f-112">Uma nova guia estática foi adicionada</span><span class="sxs-lookup"><span data-stu-id="7791f-112">A new static tab was added</span></span>
* <span data-ttu-id="7791f-113">Uma nova guia configurável foi adicionada</span><span class="sxs-lookup"><span data-stu-id="7791f-113">A new configurable tab was added</span></span>
* <span data-ttu-id="7791f-114">Propriedades dentro de "webApplicationInfo" alteradas</span><span class="sxs-lookup"><span data-stu-id="7791f-114">Properties inside "webApplicationInfo" changed</span></span>

![nova versão disponível](media/manage-your-custom-apps-update1.png)

![opção de atualização para um aplicativo](media/manage-your-custom-apps-update2.png)

> [!NOTE] 
> <span data-ttu-id="7791f-117">O processo de atualização se aplica a todas as atualizações de aplicativos para aplicativos da Microsoft, aplicativos personalizados e aplicativos de terceiros.</span><span class="sxs-lookup"><span data-stu-id="7791f-117">The update process applies to all app updates for Microsoft apps, custom apps, and third-party apps.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="7791f-118">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7791f-118">Related topics</span></span>

[<span data-ttu-id="7791f-119">Gerenciar aplicativos</span><span class="sxs-lookup"><span data-stu-id="7791f-119">Manage apps</span></span>](manage-apps.md)