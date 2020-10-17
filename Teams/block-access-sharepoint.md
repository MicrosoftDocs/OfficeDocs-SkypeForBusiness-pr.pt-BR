---
title: Bloquear o acesso ao SharePoint para usuários específicos
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: Nigolc
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
description: Saiba mais sobre como bloquear o acesso ao SharePoint para usuários específicos
ms.openlocfilehash: edcdb8286ff69557215a0e481b12e67b81f440fe
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203834"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a><span data-ttu-id="30e86-103">Bloquear o acesso ao SharePoint para usuários específicos</span><span class="sxs-lookup"><span data-stu-id="30e86-103">Block access to SharePoint for specific users</span></span>

<span data-ttu-id="30e86-104">A aplicação de qualquer política de Acesso Condicional (AC) do SharePoint no Microsoft 365 também se aplica ao Teams.</span><span class="sxs-lookup"><span data-stu-id="30e86-104">Applying any Conditional Access (CA) policy on SharePoint in Microsoft 365 is also applied to Teams.</span></span> <span data-ttu-id="30e86-105">No entanto, algumas organizações desejam bloquear o acesso aos arquivos do SharePoint (carregar, baixar, visualizar, editar, criar) e ainda permitir que seus funcionários usem clientes Web, móveis e da área de trabalho do Teams em dispositivos não gerenciados.</span><span class="sxs-lookup"><span data-stu-id="30e86-105">However, some organizations want to block access to SharePoint files (upload, download, view, edit, create) yet allow their employees to use Teams desktop, mobile, and web clients on unmanaged devices.</span></span> <span data-ttu-id="30e86-106">De acordo com as regras de política AC, o bloqueio do Sharepoint bloquearia também o Teams.</span><span class="sxs-lookup"><span data-stu-id="30e86-106">Under the CA policy rules, blocking Sharepoint would lead to blocking Teams as well.</span></span> <span data-ttu-id="30e86-107">Este artigo explica como você pode contornar essa limitação e permitir que seus funcionários continuem usando o Teams enquanto bloqueia completamente o acesso aos arquivos armazenados no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="30e86-107">This article explains how you can work around this limitation and allow your employees to continue using Teams while completely blocking access to files stored in SharePoint.</span></span>

> [!Note]
> <span data-ttu-id="30e86-108">O bloqueio ou limitação do acesso em dispositivos não gerenciados depende das políticas de acesso condicional do Microsoft Azure AD.</span><span class="sxs-lookup"><span data-stu-id="30e86-108">Blocking or limiting access on unmanaged devices relies on Azure AD conditional access policies.</span></span> <span data-ttu-id="30e86-109">Saiba mais sobre o [Licenciamento do Microsoft Azure AD](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="30e86-109">Learn about [Azure AD licensing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span> <span data-ttu-id="30e86-110">Para obter uma visão geral do acesso condicional no Microsoft Azure AD, confira [Acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="30e86-110">For an overview of conditional access in Azure AD, see [Conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span> <span data-ttu-id="30e86-111">Para obter informações sobre as políticas de acesso recomendadas do SharePoint Online, confira [Recomendações de política para proteger sites e arquivos do SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span><span class="sxs-lookup"><span data-stu-id="30e86-111">For info about recommended SharePoint Online access policies, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span> <span data-ttu-id="30e86-112">Se você limitar o acesso a dispositivos não gerenciados, os usuários de dispositivos gerenciados deverão usar um dos [sistemas operacionais e combinações de navegador com suporte](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), ou terão seu acesso limitado também.</span><span class="sxs-lookup"><span data-stu-id="30e86-112">If you limit access on unmanaged devices, users on managed devices must use one of the [supported OS and browser combinations](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), or they will also have limited access.</span></span>

<span data-ttu-id="30e86-113">Você pode bloquear ou limitar o acesso de:</span><span class="sxs-lookup"><span data-stu-id="30e86-113">You can block or limit access for:</span></span>

- <span data-ttu-id="30e86-114">Usuários da organização ou apenas alguns usuários ou grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="30e86-114">Users in the organization or only some users or security groups.</span></span>

- <span data-ttu-id="30e86-115">Todos os sites da organização ou apenas alguns deles.</span><span class="sxs-lookup"><span data-stu-id="30e86-115">All sites in the organization or only some sites.</span></span>

<span data-ttu-id="30e86-116">Quando o acesso é bloqueado, os usuários verão uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="30e86-116">When access is blocked, users will see an error message.</span></span> <span data-ttu-id="30e86-117">O bloqueio de acesso ajuda a fornecer segurança e protege dados seguros.</span><span class="sxs-lookup"><span data-stu-id="30e86-117">Blocking access helps provide security and protects secure data.</span></span> <span data-ttu-id="30e86-118">Quando o acesso é bloqueado, os usuários verão uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="30e86-118">When access is blocked, users will see an error message.</span></span>

1. <span data-ttu-id="30e86-119">Abra o Centro de Administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="30e86-119">Open the SharePoint Admin Center.</span></span>

2. <span data-ttu-id="30e86-120">Expanda **Políticas** > **Políticas de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="30e86-120">Expand **Policies** > **Access Policies**.</span></span>

3. <span data-ttu-id="30e86-121">Na seção **Dispositivos não gerenciados**, selecione **Bloquear Acesso** e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="30e86-121">In the **Unmanaged Devices** section,  select **Block Access** and select **Save**.</span></span>

   ![a seção Dispositivos não gerenciados para Políticas](media/no-sharepoint-access1.png)

4. <span data-ttu-id="30e86-123">Abra o portal do [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) e acesse **Políticas de Acesso Condicional**.</span><span class="sxs-lookup"><span data-stu-id="30e86-123">Open the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) portal and navigate to **Conditional Access Policies**.</span></span>

    <span data-ttu-id="30e86-124">Você verá uma nova política criada pelo SharePoint semelhante a este exemplo:</span><span class="sxs-lookup"><span data-stu-id="30e86-124">You'll see a new policy has been created by SharePoint that's similar to this example:</span></span>

    ![uma nova política chamada Usar restrições impostas pelo aplicativo para acesso ao navegador](media/no-sharepoint-access2.png)

5. <span data-ttu-id="30e86-126">Atualize a política para direcionar apenas a usuários ou a um grupo específicos.</span><span class="sxs-lookup"><span data-stu-id="30e86-126">Update the policy to target only specific users or a group.</span></span>

    ![o centro de administração do Sharepoint com a seção Selecionar usuário destacada.](media/no-sharepoint-access2b.png)

  > [!Note]
> <span data-ttu-id="30e86-128">Configurar essa política impedirá seu acesso ao portal de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="30e86-128">Setting this policy will cut your access to the SharePoint admin portal.</span></span> <span data-ttu-id="30e86-129">Recomendamos que você configure a política de exclusão e selecione os Administradores globais e do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="30e86-129">We recommended that you configure the exclusion policy and select the Global and SharePoint admins.</span></span>

6. <span data-ttu-id="30e86-130">Verificar se apenas o SharePoint está selecionado como Aplicativo na Nuvem de destino</span><span class="sxs-lookup"><span data-stu-id="30e86-130">Verify that only SharePoint is selected as targeted Cloud App</span></span>

    ![O SharePoint está selecionado como o aplicativo de destino.](media/no-sharepoint-access3.png)

7. <span data-ttu-id="30e86-132">Atualize as **Condições** para incluir clientes da área de trabalho também.</span><span class="sxs-lookup"><span data-stu-id="30e86-132">Update **Conditions** to include desktop clients, as well.</span></span>

    ![aplicativos móveis e da área de trabalho em destaque.](media/no-sharepoint-access4.png)

8. <span data-ttu-id="30e86-134">Certifique-se de que **Conceder acesso** está habilitado</span><span class="sxs-lookup"><span data-stu-id="30e86-134">Make sure that **Grant access** is enabled</span></span>

    ![conceder acesso está habilitado.](media/no-sharepoint-access5.png)

9. <span data-ttu-id="30e86-136">Certifique-se de que **Usar restrições impostas pelo aplicativo** está habilitado.</span><span class="sxs-lookup"><span data-stu-id="30e86-136">Make sure **Use app enforced restrictions** is enabled.</span></span>

10. <span data-ttu-id="30e86-137">Habilite sua política e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="30e86-137">Enable your policy and select **Save**.</span></span>

    ![As restrições impostas pelo aplicativo estão habilitadas.](media/no-sharepoint-access6.png)

<span data-ttu-id="30e86-139">Para testar sua política, você precisa sair de qualquer cliente, como o aplicativo da área de trabalho do Teams ou o cliente de sincronização do OneDrive for Business e entrar novamente para ver a política funcionando.</span><span class="sxs-lookup"><span data-stu-id="30e86-139">To test your policy, you need to sign out from any client such as the Teams desktop app or the OneDrive for Business sync client and sign in again to see the policy working.</span></span> <span data-ttu-id="30e86-140">Se o seu acesso tiver sido bloqueado, você verá uma mensagem no Teams informando que o item pode não existir.</span><span class="sxs-lookup"><span data-stu-id="30e86-140">If your access has been blocked, you'll see a message in Teams that states the item might not exist.</span></span>

 ![Mensagem de item não encontrado.](media/access-denied-sharepoint.png)

<span data-ttu-id="30e86-142">No Sharepoint, você receberá uma mensagem de acesso negado.</span><span class="sxs-lookup"><span data-stu-id="30e86-142">In Sharepoint, you'll receive an access denied message.</span></span>

![A mensagem de acesso negado.](media/blocked-access-warning.png)

## <a name="related-topics"></a><span data-ttu-id="30e86-144">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="30e86-144">Related topics</span></span>

[<span data-ttu-id="30e86-145">Controle o acesso a dispositivos não gerenciados no SharePoint</span><span class="sxs-lookup"><span data-stu-id="30e86-145">Control access for unmanaged devices in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
