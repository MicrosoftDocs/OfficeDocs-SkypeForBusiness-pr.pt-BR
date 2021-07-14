---
title: Implantar Teams telefones e Teams displays usando o Intune
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: Este artigo fornece uma visão geral dos recursos e com suporte Microsoft Teams exibições.
ms.openlocfilehash: ee5b536aaadaf458b6edf9b32dea299a3ecad9a0
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420816"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a><span data-ttu-id="b6b99-103">Implantar Teams telefones e Teams displays usando o Intune</span><span class="sxs-lookup"><span data-stu-id="b6b99-103">Deploy Teams phones and Teams displays using Intune</span></span>

<span data-ttu-id="b6b99-104">Este artigo fornece uma visão geral de como implantar.</span><span class="sxs-lookup"><span data-stu-id="b6b99-104">This article gives you an overview of how to deploy.</span></span> <span data-ttu-id="b6b99-105">Teams telefones e Teams exibição usando o Intune.</span><span class="sxs-lookup"><span data-stu-id="b6b99-105">Teams phones and Teams display using Intune.</span></span>

## <a name="conditional-access"></a><span data-ttu-id="b6b99-106">Acesso condicional</span><span class="sxs-lookup"><span data-stu-id="b6b99-106">Conditional Access</span></span>

<span data-ttu-id="b6b99-107">O Acesso Condicional é um recurso Azure Active Directory (Azure AD) que ajuda você a garantir que os dispositivos que acessam seus recursos Office 365 sejam gerenciados corretamente e sejam seguros.</span><span class="sxs-lookup"><span data-stu-id="b6b99-107">Conditional Access is an Azure Active Directory (Azure AD) feature that helps you to ensure devices accessing your Office 365 resources are properly managed and are secure.</span></span>  <span data-ttu-id="b6b99-108">Se você aplicar políticas de Acesso Condicional ao serviço Teams, dispositivos Android (incluindo telefones Teams e telas Teams) que o acesso Teams precisa ser inscrito no Intune e suas configurações precisam estar em conformidade com suas políticas.</span><span class="sxs-lookup"><span data-stu-id="b6b99-108">If you apply Conditional Access policies to the Teams service, Android devices (including Teams phones and Teams displays) that access Teams needs to be enrolled into Intune and their settings need to comply with your policies.</span></span>  <span data-ttu-id="b6b99-109">Se o dispositivo não estiver inscrito no Intune ou se estiver inscrito, mas suas configurações não estão em conformidade com suas políticas, o Acesso Condicional impedirá que um usuário entre ou use o aplicativo Teams no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b6b99-109">If the device isn't enrolled into Intune, or if it's enrolled but its settings don't comply with your policies, Conditional Access will prevent a user from signing in to or using the Teams app on the device.</span></span>

<span data-ttu-id="b6b99-110">Normalmente, as políticas de conformidade definidas no Intune são atribuídas a grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="b6b99-110">Typically, compliance policies defined within Intune are assigned to groups of users.</span></span>  <span data-ttu-id="b6b99-111">Isso significa que, se você atribuir uma política de conformidade do Android ao user@contoso.com, essa política se aplicará igualmente ao seu smartphone Android e a qualquer dispositivo Teams android no user@contoso.com conectado.</span><span class="sxs-lookup"><span data-stu-id="b6b99-111">This means that if you assign an Android compliance policy to user@contoso.com, that policy will apply equally to their Android smartphone and to any Android-based Teams device that user@contoso.com signs into.</span></span>

<span data-ttu-id="b6b99-112">Se você usar o Acesso Condicional, que exige que o registro do Intune seja imposto, em sua organização, há algumas coisas que você precisa configurar para permitir um registro bem-sucedido do Intune:</span><span class="sxs-lookup"><span data-stu-id="b6b99-112">If you use Conditional Access, which requires Intune enrollment to be enforced, in your organization, there are a couple things you need to set up to allow for a successful Intune enrollment:</span></span>

- <span data-ttu-id="b6b99-113">**Licença do Intune** O usuário que entra no dispositivo Teams deve ser licenciado para o Intune.</span><span class="sxs-lookup"><span data-stu-id="b6b99-113">**Intune license** The user signing into the Teams device must be licensed for Intune.</span></span>  <span data-ttu-id="b6b99-114">Desde que o dispositivo Teams seja conectado a uma conta de usuário que tenha uma licença válida do Intune, o dispositivo será automaticamente inscrito no Microsoft Intune como parte do processo de entrada.</span><span class="sxs-lookup"><span data-stu-id="b6b99-114">As long as the Teams device is signed in to a user account that has a valid Intune license, the device will automatically be enrolled in Microsoft Intune as part of the sign-in process.</span></span>
- <span data-ttu-id="b6b99-115">**Configurar o Intune** Você deve ter um locatário do Intune configurado corretamente para o registro do Administrador de Dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="b6b99-115">**Configure Intune** You must have a properly configured Intune tenant set up for Android Device Administrator enrollment.</span></span>

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a><span data-ttu-id="b6b99-116">Configurar o Intune para registrar Teams dispositivos baseados no Android</span><span class="sxs-lookup"><span data-stu-id="b6b99-116">Configure Intune to enroll Teams Android-based devices</span></span>

<span data-ttu-id="b6b99-117">Teams Os dispositivos baseados em Android são gerenciados pelo Intune por meio do gerenciamento do Administrador de Dispositivos Android (DA).</span><span class="sxs-lookup"><span data-stu-id="b6b99-117">Teams Android-based devices are managed by Intune via Android Device Administrator (DA) management.</span></span> <span data-ttu-id="b6b99-118">Antes que os dispositivos possam ser inscritos no Intune, há algumas etapas básicas a serem tomadas.</span><span class="sxs-lookup"><span data-stu-id="b6b99-118">Before devices can be enrolled into Intune, there are a few basic steps to perform.</span></span>  <span data-ttu-id="b6b99-119">Se você já está gerenciando dispositivos com o Intune hoje, provavelmente já fez todas essas coisas.</span><span class="sxs-lookup"><span data-stu-id="b6b99-119">If you are already managing devices with Intune today, you probably have already done all these things.</span></span>  <span data-ttu-id="b6b99-120">Caso não seja, veja o que fazer:</span><span class="sxs-lookup"><span data-stu-id="b6b99-120">If not, here’s what to do:</span></span>

> [!NOTE]
> - <span data-ttu-id="b6b99-121">Se os administradores de locatários quiserem que os telefones de área comum sejam inscritos no Intune, eles precisarão adicionar uma licença do Intune à conta e seguir as etapas para o registro do Intune.</span><span class="sxs-lookup"><span data-stu-id="b6b99-121">If tenant admins want common area phones to be enrolled into Intune, they need to add an Intune license to the account and follow the steps for Intune enrollment.</span></span>
> - <span data-ttu-id="b6b99-122">Se a conta de usuário usada para entrar em um dispositivo Teams não estiver licenciada para o Intune, as políticas de conformidade e as restrições de registro do Intune precisarão ser desabilitadas para a conta.</span><span class="sxs-lookup"><span data-stu-id="b6b99-122">If the user account used to sign into a Teams device isn't licensed for Intune, Intune compliance policies and enrollment restrictions need to be disabled for the account.</span></span>



1. <span data-ttu-id="b6b99-123">Definir a Autoridade do MDM do Intune (gerenciamento de dispositivo móvel).</span><span class="sxs-lookup"><span data-stu-id="b6b99-123">Set Intune MDM (mobile device management) Authority.</span></span>  

   <span data-ttu-id="b6b99-124">Se você nunca usou o Intune antes, precisa definir a autoridade MDM antes de registrar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b6b99-124">If you’ve never used Intune before, you need to set the MDM authority before you can enroll devices.</span></span> <span data-ttu-id="b6b99-125">Para obter mais informações, consulte [Definir a autoridade de gerenciamento de dispositivo móvel](/intune/fundamentals/mdm-authority-set).</span><span class="sxs-lookup"><span data-stu-id="b6b99-125">For more information, see [Set the mobile device management authority](/intune/fundamentals/mdm-authority-set).</span></span>  <span data-ttu-id="b6b99-126">Esta é uma etapa única que precisa ser feita ao criar um novo locatário do Intune.</span><span class="sxs-lookup"><span data-stu-id="b6b99-126">This is a one-time step that has to be done upon creating a new Intune tenant.</span></span>
1. <span data-ttu-id="b6b99-127">Habilitar o registro do administrador de dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="b6b99-127">Enable Android device administrator enrollment.</span></span>
  
   <span data-ttu-id="b6b99-128">Os dispositivos Teams baseados no Android são gerenciados como dispositivos administradores de dispositivos com o Intune.</span><span class="sxs-lookup"><span data-stu-id="b6b99-128">Android-based Teams devices are managed as device administrator devices with Intune.</span></span>  <span data-ttu-id="b6b99-129">O registro do administrador de dispositivos está desabilitado por padrão para locatários recém-criados.</span><span class="sxs-lookup"><span data-stu-id="b6b99-129">Device administrator enrollment is off by default for newly created tenants.</span></span> <span data-ttu-id="b6b99-130">Consulte [Registro de administrador de dispositivo Android](/intune/enrollment/android-enroll-device-administrator).</span><span class="sxs-lookup"><span data-stu-id="b6b99-130">See [Android device administrator enrollment](/intune/enrollment/android-enroll-device-administrator).</span></span>
1. <span data-ttu-id="b6b99-131">Atribuir licenças aos usuários.</span><span class="sxs-lookup"><span data-stu-id="b6b99-131">Assign licenses to users.</span></span> 
 
   <span data-ttu-id="b6b99-132">Os usuários Teams dispositivos que se registram no Intune devem ter uma licença válida do Intune.</span><span class="sxs-lookup"><span data-stu-id="b6b99-132">Users of Teams devices enrolling to Intune must be assigned a valid Intune license.</span></span> <span data-ttu-id="b6b99-133">Para obter mais informações, consulte Atribuir licenças aos usuários para [que eles possam registrar dispositivos no Intune](/intune/fundamentals/licenses-assign).</span><span class="sxs-lookup"><span data-stu-id="b6b99-133">For more information, see [Assign licenses to users so they can enroll devices in Intune](/intune/fundamentals/licenses-assign).</span></span>
1. <span data-ttu-id="b6b99-134">Atribuir políticas de conformidade do Administrador de Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b6b99-134">Assign Device Administrator compliance policies.</span></span>  

   <span data-ttu-id="b6b99-135">a.</span><span class="sxs-lookup"><span data-stu-id="b6b99-135">a.</span></span> <span data-ttu-id="b6b99-136">Crie uma política de conformidade do Administrador de Dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="b6b99-136">Create an Android Device Administrator compliance policy.</span></span>

   <span data-ttu-id="b6b99-137">b.</span><span class="sxs-lookup"><span data-stu-id="b6b99-137">b.</span></span> <span data-ttu-id="b6b99-138">Atribua-o ao grupo Azure Active Directory que contém os usuários que entrarão no Teams dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b6b99-138">Assign it to the Azure Active Directory group that contains the users that will be signing into the Teams devices.</span></span> <span data-ttu-id="b6b99-139">Consulte [Usar políticas de conformidade para definir regras para dispositivos que você gerencia com o Intune](/mem/intune/protect/device-compliance-get-started).</span><span class="sxs-lookup"><span data-stu-id="b6b99-139">See [Use compliance policies to set rules for devices you manage with Intune](/mem/intune/protect/device-compliance-get-started).</span></span>

## <a name="see-also"></a><span data-ttu-id="b6b99-140">Confira também</span><span class="sxs-lookup"><span data-stu-id="b6b99-140">See also</span></span>

[<span data-ttu-id="b6b99-141">Telefones para o Teams</span><span class="sxs-lookup"><span data-stu-id="b6b99-141">Phones for Teams</span></span>](phones-for-teams.md)

[<span data-ttu-id="b6b99-142">Telefones IP certificados para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b6b99-142">IP Phones certified for Microsoft Teams</span></span>](teams-ip-phones.md)

[<span data-ttu-id="b6b99-143">Teams exibe</span><span class="sxs-lookup"><span data-stu-id="b6b99-143">Teams displays</span></span>](teams-displays.md)

[<span data-ttu-id="b6b99-144">Gerenciar seus dispositivos no Teams</span><span class="sxs-lookup"><span data-stu-id="b6b99-144">Manage your devices in Teams</span></span>](device-management.md)

[<span data-ttu-id="b6b99-145">Teams Marketplace</span><span class="sxs-lookup"><span data-stu-id="b6b99-145">Teams Marketplace</span></span>](https://office.com/teamsdevices)