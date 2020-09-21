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
ms.openlocfilehash: 959de8c06e26d2d12c3a3698375b11d373392447
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955970"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a><span data-ttu-id="1e850-103">Bloquear o acesso ao SharePoint para usuários específicos</span><span class="sxs-lookup"><span data-stu-id="1e850-103">Block access to SharePoint for specific users</span></span>

<span data-ttu-id="1e850-104">A aplicação de qualquer política de acesso condicional (CA) no SharePoint Online (SPO) também é aplicada ao Teams.</span><span class="sxs-lookup"><span data-stu-id="1e850-104">Applying any Conditional Access (CA) policy on SharePoint Online (SPO) is also applied to Teams.</span></span> <span data-ttu-id="1e850-105">No entanto, algumas organizações desejam bloquear o acesso aos arquivos do SharePoint (carregar, baixar, exibir, editar, criar) ainda permitem que seus funcionários usem clientes da área de trabalho do Teams, dispositivos móveis e Web em dispositivos não gerenciados.</span><span class="sxs-lookup"><span data-stu-id="1e850-105">However, some organizations want to block access to SharePoint files (upload, download, view, edit, create) yet allow their employees to use Teams desktop, mobile, and web clients on unmanaged devices.</span></span> <span data-ttu-id="1e850-106">Nas regras de política da autoridade de certificação, o bloqueio de SPO também levaria a bloquear o Teams.</span><span class="sxs-lookup"><span data-stu-id="1e850-106">Under the CA policy rules, blocking SPO would lead to blocking Teams as well.</span></span> <span data-ttu-id="1e850-107">Este artigo explica como você pode contornar essa limitação e permitir que seus funcionários continuem a usar o Teams enquanto bloqueiam completamente o acesso a arquivos armazenados no SPO.</span><span class="sxs-lookup"><span data-stu-id="1e850-107">This article explains how you can work around this limitation and allow your employees to continue using Teams while completely blocking access to files stored in SPO.</span></span>

> [!Note]
> <span data-ttu-id="1e850-108">Bloquear ou limitar o acesso em dispositivos não gerenciados depende das políticas de acesso condicional do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1e850-108">Blocking or limiting access on unmanaged devices relies on Azure AD conditional access policies.</span></span> <span data-ttu-id="1e850-109">Saiba mais sobre o [Licenciamento do Azure ad](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="1e850-109">Learn about [Azure AD licensing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span> <span data-ttu-id="1e850-110">Para obter uma visão geral do acesso condicional no Azure AD, consulte [acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="1e850-110">For an overview of conditional access in Azure AD, see [Conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span> <span data-ttu-id="1e850-111">Para obter informações sobre as políticas de acesso recomendadas do SharePoint, consulte [recomendações de política para proteger sites e arquivos do SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span><span class="sxs-lookup"><span data-stu-id="1e850-111">For info about recommended SharePoint access policies, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span> <span data-ttu-id="1e850-112">Se você limitar o acesso em dispositivos não gerenciados, os usuários em dispositivos gerenciados devem usar uma das [combinações de sistema operacional e navegador compatíveis](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition)ou também terão acesso limitado.</span><span class="sxs-lookup"><span data-stu-id="1e850-112">If you limit access on unmanaged devices, users on managed devices must use one of the [supported OS and browser combinations](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), or they will also have limited access.</span></span>

<span data-ttu-id="1e850-113">Você pode bloquear ou limitar o acesso para:</span><span class="sxs-lookup"><span data-stu-id="1e850-113">You can block or limit access for:</span></span>

- <span data-ttu-id="1e850-114">Usuários na organização ou somente alguns usuários ou grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="1e850-114">Users in the organization or only some users or security groups.</span></span>

- <span data-ttu-id="1e850-115">Todos os sites da organização ou somente alguns sites.</span><span class="sxs-lookup"><span data-stu-id="1e850-115">All sites in the organization or only some sites.</span></span>

<span data-ttu-id="1e850-116">Quando o Access estiver bloqueado, os usuários verão uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="1e850-116">When access is blocked, users will see an error message.</span></span> <span data-ttu-id="1e850-117">O bloqueio do Access ajuda a oferecer segurança e protege dados protegidos.</span><span class="sxs-lookup"><span data-stu-id="1e850-117">Blocking access helps provide security and protects secure data.</span></span> <span data-ttu-id="1e850-118">Quando o Access estiver bloqueado, os usuários verão uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="1e850-118">When access is blocked, users will see an error message.</span></span>

1. <span data-ttu-id="1e850-119">Abra o [centro de administração](https://admin.microsoft.com/sharepoint?page=accessControl&modern=true)do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1e850-119">Open the SharePoint [Admin Center](https://admin.microsoft.com/sharepoint?page=accessControl&modern=true).</span></span>

2. <span data-ttu-id="1e850-120">Expanda políticas de **Policies**  >  **acesso às**políticas.</span><span class="sxs-lookup"><span data-stu-id="1e850-120">Expand **Policies** > **Access Policies**.</span></span>

3. <span data-ttu-id="1e850-121">Na seção **dispositivos não gerenciados** , selecione **bloquear acesso** e selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="1e850-121">In the **Unmanaged Devices** section,  select **Block Access** and select **Save**.</span></span>

   ![a seção dispositivos não gerenciados para políticas](media/no-sharepoint-access1.png)

4. <span data-ttu-id="1e850-123">Abra o portal [do Active Directory do Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) e navegue até **políticas de acesso condicional**.</span><span class="sxs-lookup"><span data-stu-id="1e850-123">Open the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) portal and navigate to **Conditional Access Policies**.</span></span>

    <span data-ttu-id="1e850-124">Você verá que uma nova política foi criada pelo SharePoint semelhante a este exemplo:</span><span class="sxs-lookup"><span data-stu-id="1e850-124">You'll see a new policy has been created by SharePoint that's similar to this example:</span></span>

    ![uma nova política nomeada usar restrições impostas pelo aplicativo para acesso ao navegador](media/no-sharepoint-access2.png)

5. <span data-ttu-id="1e850-126">Atualize a política para direcionar apenas usuários específicos ou um grupo.</span><span class="sxs-lookup"><span data-stu-id="1e850-126">Update the policy to target only specific users or a group.</span></span>

    ![o centro de administração do SharePoint com a seção Selecionar usuário realçada.](media/no-sharepoint-access2b.png)

  > [!Note]
> <span data-ttu-id="1e850-128">A configuração desta política recortará seu acesso ao portal de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1e850-128">Setting this policy will cut your access to the SharePoint admin portal.</span></span> <span data-ttu-id="1e850-129">Recomendamos que você configure a política de exclusão e selecione os administradores globais e do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1e850-129">We recommended that you configure the exclusion policy and select the Global and SharePoint admins.</span></span>

6. <span data-ttu-id="1e850-130">Verificar se apenas o SharePoint Online está selecionado como aplicativo de nuvem direcionado</span><span class="sxs-lookup"><span data-stu-id="1e850-130">Verify that only SharePoint Online is selected as targeted Cloud App</span></span>

    ![O SharePoint Online está selecionado como o aplicativo de destino.](media/no-sharepoint-access3.png)

7. <span data-ttu-id="1e850-132">Atualize **condições** para incluir clientes da área de trabalho também.</span><span class="sxs-lookup"><span data-stu-id="1e850-132">Update **Conditions** to include desktop clients, as well.</span></span>

    ![aplicativos de área de trabalho e móveis realçados.](media/no-sharepoint-access4.png)

8. <span data-ttu-id="1e850-134">Verifique se a opção **conceder acesso** está habilitada</span><span class="sxs-lookup"><span data-stu-id="1e850-134">Make sure that **Grant access** is enabled</span></span>

    ![conceder acesso está habilitado.](media/no-sharepoint-access5.png)

9. <span data-ttu-id="1e850-136">Certifique-se de que a opção **usar restrições impostas de aplicativo** esteja habilitada.</span><span class="sxs-lookup"><span data-stu-id="1e850-136">Make sure **Use app enforced restrictions** is enabled.</span></span>

10. <span data-ttu-id="1e850-137">Habilite a política e selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="1e850-137">Enable your policy and select **Save**.</span></span>

    ![As restrições do aplicativo Enforced estão habilitadas.](media/no-sharepoint-access6.png)

<span data-ttu-id="1e850-139">Para testar sua política, você precisa desconectar-se de qualquer cliente, como o aplicativo da área de trabalho Teams ou o cliente de sincronização do OneDrive, e entrar novamente para ver a política em funcionamento.</span><span class="sxs-lookup"><span data-stu-id="1e850-139">To test your policy, you need to sign out from any client such as the Teams desktop app or the OneDrive sync client and sign in again to see the policy working.</span></span> <span data-ttu-id="1e850-140">Se o seu acesso tiver sido bloqueado, você verá uma mensagem em Teams que informa que o item pode não existir.</span><span class="sxs-lookup"><span data-stu-id="1e850-140">If your access has been blocked, you'll see a message in Teams that states the item might not exist.</span></span>

 ![A mensagem item não encontrado.](media/access-denied-sharepoint.png)

<span data-ttu-id="1e850-142">No SharePoint, você receberá uma mensagem de acesso negado.</span><span class="sxs-lookup"><span data-stu-id="1e850-142">In Sharepoint, you'll receive an access denied message.</span></span> 

![A mensagem de acesso negado.](media/blocked-access-warning.png)

## <a name="related-topics"></a><span data-ttu-id="1e850-144">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1e850-144">Related topics</span></span>

[<span data-ttu-id="1e850-145">Controlar o acesso a dispositivos não gerenciados no SharePoint</span><span class="sxs-lookup"><span data-stu-id="1e850-145">Control access for unmanaged devices in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
