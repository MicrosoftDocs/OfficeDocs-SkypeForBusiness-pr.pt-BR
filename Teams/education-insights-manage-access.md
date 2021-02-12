---
title: Gerenciar acesso do usuário ao Education Insights
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Gerenciar acesso do usuário ao Education Insights no Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32bd773975ff6b67d28ab765ffa7c932e978af7d
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145928"
---
# <a name="manage-user-access-to-education-insights"></a><span data-ttu-id="0ec81-103">Gerenciar acesso do usuário ao Education Insights</span><span class="sxs-lookup"><span data-stu-id="0ec81-103">Manage user access to Education Insights</span></span>

<span data-ttu-id="0ec81-104">Este documento descreve as etapas necessárias para gerenciar o acesso do usuário ao [Education Insights no Microsoft Teams](class-insights.md).</span><span class="sxs-lookup"><span data-stu-id="0ec81-104">This document provides the steps required to manage user access to [Education Insights in Microsoft Teams](class-insights.md).</span></span>

<span data-ttu-id="0ec81-105">Você precisa fornecer permissões para gestores escolares, inspetores, diretores de escola, professores-gestores, conselheiros, coordenadores pedagógicos, diretores de programas, assistentes sociais e psicólogos.</span><span class="sxs-lookup"><span data-stu-id="0ec81-105">You need to provide permissions for education leaders, district leaders, school principals, head teachers, counselors, heads of learning areas, program directors, social workers, and psychologists.</span></span> <span data-ttu-id="0ec81-106">Os educadores *automaticamente* recebem permissão quando possuem uma equipe de classe.</span><span class="sxs-lookup"><span data-stu-id="0ec81-106">Educators are *automatically* given permission when they own a class team.</span></span>

<span data-ttu-id="0ec81-107">Para fornecer o Insights no nível da organização, você deve [importar dados do Sistema de Informações do Aluno (SIS)](education-insights-sis-data-sync.md) de forma que o Insights tenha estrutura hierárquica do sistema educacional mapeada corretamente.</span><span class="sxs-lookup"><span data-stu-id="0ec81-107">To provide organization-level Insights, you must [import data from the Student Information System (SIS)](education-insights-sis-data-sync.md) so that Insights has the hierarchical structure of the educational system mapped correctly.</span></span>

> [!NOTE]
> <span data-ttu-id="0ec81-108">Apenas o Administrador Global pode gerenciar o acesso do usuário ao Insights.</span><span class="sxs-lookup"><span data-stu-id="0ec81-108">Only Global Administrator can manage user access to Insights.</span></span>

> [!TIP]
> <span data-ttu-id="0ec81-109">Recomendamos que você habilite o insights para todos seus líderes de educação para que eles tenham os dados para entender cada escola, e a capacidade de identificar rapidamente os problemas e fornecer suporte aos seus educadores.</span><span class="sxs-lookup"><span data-stu-id="0ec81-109">We recommend that you enable Insights for all your education leaders so that they have the data to understand each school, and the ability to quickly identify problems and provide support to their educators.</span></span> <span data-ttu-id="0ec81-110">Mesmo que você esteja executando um projeto piloto, ainda pode ser útil manter o Insights habilitado para todos os líderes da educação, mas só direcionar as comunicações para o grupo piloto de usuários.</span><span class="sxs-lookup"><span data-stu-id="0ec81-110">Even if you're running a pilot, it may still be helpful to keep Insights enabled for all education leaders, but only target communications to the pilot group of users.</span></span>



## <a name="grant-permissions"></a><span data-ttu-id="0ec81-111">Conceda permissões.</span><span class="sxs-lookup"><span data-stu-id="0ec81-111">Grant permissions</span></span>

* <span data-ttu-id="0ec81-112">Abra o aplicativo Insights, clique em **Configurações** e, selecione **Permissões de usuário**</span><span class="sxs-lookup"><span data-stu-id="0ec81-112">Open the Insights app, click **Settings**, and select **User permissions**</span></span>

:::image type="content" source="media/insights-user-permissions.png" alt-text="Configurações":::

* <span data-ttu-id="0ec81-114">Selecione **Adicionar usuários**.</span><span class="sxs-lookup"><span data-stu-id="0ec81-114">Select **Add users**.</span></span>
* <span data-ttu-id="0ec81-115">Insira o nome de usuário ou endereço de email de cada usuário.</span><span class="sxs-lookup"><span data-stu-id="0ec81-115">Enter the username or email address of each user.</span></span>
* <span data-ttu-id="0ec81-116">Selecionar o nível de permissão:</span><span class="sxs-lookup"><span data-stu-id="0ec81-116">Select the permission level:</span></span>
  * <span data-ttu-id="0ec81-117">**Acesso a toda organização** significa que o usuário vê todas as unidades da organização em todos os níveis.</span><span class="sxs-lookup"><span data-stu-id="0ec81-117">**Access to all organization** means the user sees all the org units at all levels.</span></span>
  * <span data-ttu-id="0ec81-118">**Acesso a escolas específicas** significa que o usuário vê as escolas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="0ec81-118">**Access to specific schools** means the user sees the selected schools.</span></span> <span data-ttu-id="0ec81-119">Comece a digitar e selecione a escola a partir da lista.</span><span class="sxs-lookup"><span data-stu-id="0ec81-119">Start typing and select the school from the list.</span></span> <span data-ttu-id="0ec81-120">Você pode adicionar várias escolas simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="0ec81-120">You can add multiple schools together.</span></span>
* <span data-ttu-id="0ec81-121">Clique **Adicionar novos usuários**.</span><span class="sxs-lookup"><span data-stu-id="0ec81-121">Click **Add new users**.</span></span>

:::image type="content" source="media/insights-add-users.png" alt-text="Conceder permissões":::

> [!NOTE]
> <span data-ttu-id="0ec81-123">Somente dê permissão aos líderes escolares que precisam delas e somente às unidades organizacionais pelas quais são responsáveis.</span><span class="sxs-lookup"><span data-stu-id="0ec81-123">Only provide permission to those education leaders that need them and only to the organizational units they are responsible for.</span></span> <span data-ttu-id="0ec81-124">Se você não tiver certeza se é necessária a permissão do usuário para uma organização específica, consulte os especialistas em assuntos de privacidade de sua instituição, tais como o pessoal do departamento jurídico ou do RH.</span><span class="sxs-lookup"><span data-stu-id="0ec81-124">If you are unsure whether user permission for a specific organization is required, consult your institution's privacy subject matter experts, such as legal or HR personnel.</span></span>

## <a name="edit-permissions"></a><span data-ttu-id="0ec81-125">Editar permissões</span><span class="sxs-lookup"><span data-stu-id="0ec81-125">Edit permissions</span></span>
* <span data-ttu-id="0ec81-126">Selecione um usuário específico e, em seguida, selecione **Editar permissões**.</span><span class="sxs-lookup"><span data-stu-id="0ec81-126">Select specific user, then select **Edit permissions**.</span></span>
* <span data-ttu-id="0ec81-127">Atualize o nível de permissão ou a lista de escolas, e clique em **Atualizar permissões**.</span><span class="sxs-lookup"><span data-stu-id="0ec81-127">Update the permission level or schools list, and click **Update permissions**.</span></span>

:::image type="content" source="media/insights-edit-users.png" alt-text="Editar permissões":::

## <a name="remove-permissions"></a><span data-ttu-id="0ec81-129">Remover permissões</span><span class="sxs-lookup"><span data-stu-id="0ec81-129">Remove permissions</span></span>
* <span data-ttu-id="0ec81-130">Selecione o usuário que você deseja remover e, em seguida, selecione **Remover usuários**.</span><span class="sxs-lookup"><span data-stu-id="0ec81-130">Select the users you want to remove, then select **Remove users**.</span></span>
* <span data-ttu-id="0ec81-131">Esses usuários não têm mais acesso ao Insights a nível da organização, mas ainda poderão acessar o Insights a nível de classe se possuírem uma equipe de classe.</span><span class="sxs-lookup"><span data-stu-id="0ec81-131">These users no longer have access to organization-level Insights, but can still access class-level Insights if they own a class team.</span></span>

:::image type="content" source="media/insights-remove-users.png" alt-text="Remover permissões":::
