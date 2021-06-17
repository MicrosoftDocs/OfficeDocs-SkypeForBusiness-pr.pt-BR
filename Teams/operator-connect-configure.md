---
title: Configurar Conexão do Operador
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Saiba mais sobre como configurar o Operator Connect.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4f4ec3d1d7cf39402da562e5939d794ac9f1624
ms.sourcegitcommit: 1b057bfcc3207960b956962845fd5051afe91722
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2021
ms.locfileid: "52947573"
---
# <a name="configure-operator-connect"></a><span data-ttu-id="50d16-103">Configurar Conexão do Operador</span><span class="sxs-lookup"><span data-stu-id="50d16-103">Configure Operator Connect</span></span>

>[!NOTE]
><span data-ttu-id="50d16-104">O Operator Connect está disponível apenas na **visualização pública**.</span><span class="sxs-lookup"><span data-stu-id="50d16-104">Operator Connect is currently available only in **public preview**.</span></span> <span data-ttu-id="50d16-105">A visualização pública permite testar os recursos futuros e fornecer comentários.</span><span class="sxs-lookup"><span data-stu-id="50d16-105">Public preview allows you to test upcoming features and provide feedback.</span></span> <span data-ttu-id="50d16-106">Os recursos incluídos na visualização pública podem não estar completos, podem sofrer alterações e não têm suporte no Office 365 Government Clouds.</span><span class="sxs-lookup"><span data-stu-id="50d16-106">Features included in public preview may not be complete, may undergo changes, and are not supported in Office 365 Government Clouds.</span></span>

<span data-ttu-id="50d16-107">Este artigo descreve como configurar o Operator Connect.</span><span class="sxs-lookup"><span data-stu-id="50d16-107">This article describes how to configure Operator Connect.</span></span> <span data-ttu-id="50d16-108">Antes de configurar o Operator Connect, leia [Plan for Operator Connect](operator-connect-plan.md) para obter informações sobre pré-requisitos e licenciamento.</span><span class="sxs-lookup"><span data-stu-id="50d16-108">Before configuring Operator Connect, be sure to read [Plan for Operator Connect](operator-connect-plan.md) for information about prerequisites and licensing.</span></span>

## <a name="enable-an-operator"></a><span data-ttu-id="50d16-109">Habilitar um operador</span><span class="sxs-lookup"><span data-stu-id="50d16-109">Enable an operator</span></span>

<span data-ttu-id="50d16-110">Você pode habilitar, editar e remover operadores no Centro de Administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="50d16-110">You can enable, edit, and remove operators in the Teams Admin Center.</span></span> <span data-ttu-id="50d16-111">No painel de navegação esquerdo, vá para **Voice > Operators**.</span><span class="sxs-lookup"><span data-stu-id="50d16-111">In the left navigation pane, go to **Voice > Operators**.</span></span>

<span data-ttu-id="50d16-112">Para habilitar um operador:</span><span class="sxs-lookup"><span data-stu-id="50d16-112">To enable an operator:</span></span>

1. <span data-ttu-id="50d16-113">**Escolha um operador.**</span><span class="sxs-lookup"><span data-stu-id="50d16-113">**Choose an operator.**</span></span> <span data-ttu-id="50d16-114">Na guia **Todos os operadores,** filtre operadores disponíveis por região ou serviço para encontrar o operador certo para suas necessidades de voz.</span><span class="sxs-lookup"><span data-stu-id="50d16-114">In the **All operators** tab, filter available operators by region or service to find the right operator for your voice needs.</span></span> <span data-ttu-id="50d16-115">Em seguida, selecione o operador que você deseja habilitar.</span><span class="sxs-lookup"><span data-stu-id="50d16-115">Then select the operator you want to enable.</span></span>  

2. <span data-ttu-id="50d16-116">**Selecione países.**</span><span class="sxs-lookup"><span data-stu-id="50d16-116">**Select countries.**</span></span> <span data-ttu-id="50d16-117">Em **Configurações de operador**, selecione os países que você deseja habilitar com o operador selecionado.</span><span class="sxs-lookup"><span data-stu-id="50d16-117">Under **Operator settings**, select the countries you want to enable with your selected operator.</span></span>

3. <span data-ttu-id="50d16-118">**Forneça informações de contato (opcional).**</span><span class="sxs-lookup"><span data-stu-id="50d16-118">**Provide contact information (optional).**</span></span> <span data-ttu-id="50d16-119">Se quiser que os operadores contatem você com informações adicionais sobre o Operator Connect, marque a caixa e forneça suas informações de contato.</span><span class="sxs-lookup"><span data-stu-id="50d16-119">If you want operators to contact you with additional information about Operator Connect, check the box and provide your contact information.</span></span>  

4. <span data-ttu-id="50d16-120">**Aceite o aviso de transferência de dados.**</span><span class="sxs-lookup"><span data-stu-id="50d16-120">**Accept the data transfer notice.**</span></span>

5. <span data-ttu-id="50d16-121">**Adicione seu operador.**</span><span class="sxs-lookup"><span data-stu-id="50d16-121">**Add your operator.**</span></span> <span data-ttu-id="50d16-122">Selecione **Adicionar como meu operador** para salvar.</span><span class="sxs-lookup"><span data-stu-id="50d16-122">Select **Add as my operator** to save.</span></span>

## <a name="set-up-phone-numbers"></a><span data-ttu-id="50d16-123">Configurar números de telefone</span><span class="sxs-lookup"><span data-stu-id="50d16-123">Set up phone numbers</span></span>

<span data-ttu-id="50d16-124">A configuração dos números de telefone depende da configuração de números para novos usuários ou da movimentação de números existentes dos Planos de Chamadas da Microsoft ou do Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="50d16-124">How you set up phone numbers depends on whether you're setting up numbers for new users, or moving existing numbers from either Microsoft Calling Plans or Direct Routing.</span></span>

- <span data-ttu-id="50d16-125">Se você precisar adquirir números de telefone para novos usuários, consulte [Adquirir números para novos usuários do Teams.](#acquire-numbers-for-new-teams-users)</span><span class="sxs-lookup"><span data-stu-id="50d16-125">If you need to acquire phone numbers for new users, see [Acquire numbers for new Teams users](#acquire-numbers-for-new-teams-users).</span></span>

- <span data-ttu-id="50d16-126">Se você quiser mover números existentes de Planos de Chamada para Conexão de Operador, consulte Mover números de [Planos de Chamada para Conexão do Operador](#move-numbers-from-calling-plans-to-operator-connect).</span><span class="sxs-lookup"><span data-stu-id="50d16-126">If you want to move existing numbers from Calling Plans to Operator Connect, see [Move numbers from Calling Plans to Operator Connect](#move-numbers-from-calling-plans-to-operator-connect).</span></span>

- <span data-ttu-id="50d16-127">Se você quiser mover números existentes de Roteamento Direto para Conexão de Operador, consulte [Move numbers from Direct Routing to Operator Connect](#move-numbers-from-direct-routing-to-operator-connect).</span><span class="sxs-lookup"><span data-stu-id="50d16-127">If you want to move existing numbers from Direct Routing to Operator Connect, see [Move numbers from Direct Routing to Operator Connect](#move-numbers-from-direct-routing-to-operator-connect).</span></span>

>[!IMPORTANT]
><span data-ttu-id="50d16-128">**Endereços de emergência:** Os números de telefone associados a endereços de emergência são gerenciados pela operadora.</span><span class="sxs-lookup"><span data-stu-id="50d16-128">**Emergency addresses:** Phone numbers associated with emergency addresses are managed by your operator.</span></span> <span data-ttu-id="50d16-129">Depois de criar endereços de emergência no centro de administração do Teams, sua operadora atribuirá números de telefone a esses endereços de emergência.</span><span class="sxs-lookup"><span data-stu-id="50d16-129">Once you create emergency addresses in the Teams admin center, your operator will assign phone numbers to those emergency addresses.</span></span> <span data-ttu-id="50d16-130">Para fazer alterações nos endereços de emergência e nos números de telefone atribuídos, entre em contato com sua operadora.</span><span class="sxs-lookup"><span data-stu-id="50d16-130">To make changes to emergency addresses and their assigned phone numbers, contact your operator.</span></span>

### <a name="acquire-numbers-for-new-teams-users"></a><span data-ttu-id="50d16-131">Adquirir números para novos usuários do Teams</span><span class="sxs-lookup"><span data-stu-id="50d16-131">Acquire numbers for new Teams users</span></span>

<span data-ttu-id="50d16-132">Para adquirir números para novos usuários do Teams, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="50d16-132">To acquire numbers for new Teams users, follow these steps:</span></span>

1. <span data-ttu-id="50d16-133">**Atribuir uma licença do Sistema de Telefonia.**</span><span class="sxs-lookup"><span data-stu-id="50d16-133">**Assign a Phone System license.**</span></span> <span data-ttu-id="50d16-134">Você pode atribuir uma licença do Sistema de Telefonia aos usuários do Centro de administração do Microsoft 365 ou usar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50d16-134">You can assign a Phone System license to your users from the Microsoft 365 admin center or using PowerShell.</span></span> <span data-ttu-id="50d16-135">Para obter mais informações, [consulte Atribuir licenças de complemento do Teams aos usuários](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="50d16-135">For more information, see [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>

2. <span data-ttu-id="50d16-136">**Certifique-se de estar no modo somente do Teams.**</span><span class="sxs-lookup"><span data-stu-id="50d16-136">**Make sure you're in Teams only mode.**</span></span> <span data-ttu-id="50d16-137">Para verificar se sua organização está no modo somente do Teams, no centro de administração do Teams, acesse Configurações em toda a organização > **atualização do Teams.**</span><span class="sxs-lookup"><span data-stu-id="50d16-137">To check if your organization is in Teams only mode, in the Teams admin center, go to **Org-wide settings > Teams upgrade**.</span></span> <span data-ttu-id="50d16-138">Para verificar se um usuário está no modo somente do Teams, vá para **Usuários** e selecione uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="50d16-138">To check if a user is in Teams only mode, go to **Users** and select a user account.</span></span> <span data-ttu-id="50d16-139">Na guia **Conta,** em **Atualização do Teams,** verifique se o modo de coexistência está definido como 'Somente Equipes'.</span><span class="sxs-lookup"><span data-stu-id="50d16-139">In the **Account** tab, under **Teams upgrade,** verify that your coexistence mode is set to 'Teams only.'</span></span>

3. <span data-ttu-id="50d16-140">**Crie e valide endereços de emergência.**</span><span class="sxs-lookup"><span data-stu-id="50d16-140">**Create and validate emergency addresses.**</span></span> <span data-ttu-id="50d16-141">No Centro de administração do Teams, vá até Locais > **endereços** de emergência para configurar endereços de emergência.</span><span class="sxs-lookup"><span data-stu-id="50d16-141">In the Teams admin center, go to **Locations > Emergency addresses** to set up emergency addresses.</span></span> <span data-ttu-id="50d16-142">Para saber mais, confira [Adicionar, alterar ou remover um local de emergência para sua organização.](add-change-remove-emergency-location-organization.md)</span><span class="sxs-lookup"><span data-stu-id="50d16-142">To learn more, see [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md).</span></span>

4. <span data-ttu-id="50d16-143">**Adquirir números.**</span><span class="sxs-lookup"><span data-stu-id="50d16-143">**Acquire numbers.**</span></span> <span data-ttu-id="50d16-144">Acesse o site da sua operadora para solicitar e adquirir números de telefone.</span><span class="sxs-lookup"><span data-stu-id="50d16-144">Go to your operator's website to order and acquire phone numbers.</span></span> <span data-ttu-id="50d16-145">Para ver uma lista de sites de operadores, consulte [Operators](#operators).</span><span class="sxs-lookup"><span data-stu-id="50d16-145">For a list of operator websites, see [Operators](#operators).</span></span> <span data-ttu-id="50d16-146">Você precisará fornecer sua ID de locatário.</span><span class="sxs-lookup"><span data-stu-id="50d16-146">You'll need to provide your tenant ID.</span></span> <span data-ttu-id="50d16-147">Se você não conhece sua ID de locatário, consulte Encontre sua ID de locatário do [Microsoft 365](/onedrive/find-your-office-365-tenant-id) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50d16-147">If you don't know your tenant ID, see [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id) for more information.</span></span>

5. <span data-ttu-id="50d16-148">**Atribuir números.**</span><span class="sxs-lookup"><span data-stu-id="50d16-148">**Assign numbers.**</span></span> <span data-ttu-id="50d16-149">Depois que o operador concluir o pedido, ele carregará números no locatário.</span><span class="sxs-lookup"><span data-stu-id="50d16-149">Once your operator completes the order, they'll upload numbers to your tenant.</span></span> <span data-ttu-id="50d16-150">Você pode exibir os números e o provedor no centro de administração do Teams indo para **Voz > Números de telefone**.</span><span class="sxs-lookup"><span data-stu-id="50d16-150">You can view the numbers and the provider in the Teams admin center by going to **Voice > Phone numbers**.</span></span> <span data-ttu-id="50d16-151">Atribua números aos usuários usando o Centro de administração do Teams ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50d16-151">Assign numbers to users by using the Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="50d16-152">Para obter mais informações, consulte [Atribuir números](#assign-numbers).</span><span class="sxs-lookup"><span data-stu-id="50d16-152">For more information, see [Assign numbers](#assign-numbers).</span></span>
 

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a><span data-ttu-id="50d16-153">Mover números de Planos de Chamada para Conexão de Operador</span><span class="sxs-lookup"><span data-stu-id="50d16-153">Move numbers from Calling Plans to Operator Connect</span></span>

1. <span data-ttu-id="50d16-154">Entre em contato com seu operador para por seus números para o Operator Connect.</span><span class="sxs-lookup"><span data-stu-id="50d16-154">Contact your operator to port your numbers to Operator Connect.</span></span> <span data-ttu-id="50d16-155">Consulte [Operadores](#operators) para encontrar o site da sua operadora.</span><span class="sxs-lookup"><span data-stu-id="50d16-155">See [Operators](#operators) to find your operator's website.</span></span>

2. <span data-ttu-id="50d16-156">Depois que o operador concluir a ordem de portação, você poderá desatar os números de telefone do Plano de Chamadas dos usuários e remover a Licença do Plano de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="50d16-156">After your operator completes the porting order, you can unassign your users' Calling Plan phone numbers, and remove the Calling Plan License.</span></span> <span data-ttu-id="50d16-157">Em seguida, seu operador pode carregar os números em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="50d16-157">Then, your operator can upload the numbers to your tenant.</span></span>

3. <span data-ttu-id="50d16-158">Atribua números de Conexão de Operador aos usuários usando o Centro de administração do Teams ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50d16-158">Assign Operator Connect numbers to users by using the Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="50d16-159">Para obter mais informações, consulte [Atribuir números](#assign-numbers).</span><span class="sxs-lookup"><span data-stu-id="50d16-159">For more information, see [Assign numbers](#assign-numbers).</span></span>

 
### <a name="move-numbers-from-direct-routing-to-operator-connect"></a><span data-ttu-id="50d16-160">Mover números do Roteamento Direto para o Operator Connect</span><span class="sxs-lookup"><span data-stu-id="50d16-160">Move numbers from Direct Routing to Operator Connect</span></span>

1. <span data-ttu-id="50d16-161">Remova o número de telefone existente do usuário da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="50d16-161">Remove the existing telephone number from the user as follows:</span></span>  

   <span data-ttu-id="50d16-162">Obter o URI de linha on-prem existente executando o seguinte comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="50d16-162">Get the existing On-prem Line URI by running the following PowerShell command:</span></span>

   ```
   Get-CsOnlineUser -Identity <user> | select OnPremLineURI 
   ```

   <span data-ttu-id="50d16-163">Remova o URI on-prem Line executando o seguinte comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="50d16-163">Remove the On-prem Line URI by running the following PowerShell command:</span></span>  

   ```
   Set-CsUser -identity <user> - OnPremLineURI $null 
   ```

2. <span data-ttu-id="50d16-164">Remova qualquer PSTNUsage associado aos seus usuários, caso contrário, as chamadas serão roteadas para o gateway especificado no Uso de PSTN.</span><span class="sxs-lookup"><span data-stu-id="50d16-164">Remove any PSTNUsage associated with your users, otherwise calls will be routed to the gateway specified in the PSTN Usage.</span></span> <span data-ttu-id="50d16-165">Para saber como remover o uso de PSTN, consulte [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="50d16-165">To learn how to remove PSTN usage, see [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps).</span></span>

3. <span data-ttu-id="50d16-166">Acesse o site da sua operadora para solicitar e adquirir números de telefone.</span><span class="sxs-lookup"><span data-stu-id="50d16-166">Go to your operator's website to order and acquire phone numbers.</span></span> <span data-ttu-id="50d16-167">Para ver uma lista de sites de operadores, consulte [Operators](#operators).</span><span class="sxs-lookup"><span data-stu-id="50d16-167">For a list of operator websites, see [Operators](#operators).</span></span> <span data-ttu-id="50d16-168">Você precisará fornecer sua ID de locatário.</span><span class="sxs-lookup"><span data-stu-id="50d16-168">You'll need to provide your tenant ID.</span></span> <span data-ttu-id="50d16-169">Se você não conhece sua ID de locatário, consulte Encontre sua ID de locatário do [Microsoft 365](/onedrive/find-your-office-365-tenant-id) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50d16-169">If you don't know your tenant ID, see [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id) for more information.</span></span>

4. <span data-ttu-id="50d16-170">Depois que o operador concluir o pedido, ele carregará números no locatário.</span><span class="sxs-lookup"><span data-stu-id="50d16-170">Once your operator completes the order, they'll upload numbers to your tenant.</span></span> <span data-ttu-id="50d16-171">Você pode exibir os números e o provedor no centro de administração do Teams indo para **Voz > Números de telefone**.</span><span class="sxs-lookup"><span data-stu-id="50d16-171">You can view the numbers and the provider in the Teams admin center by going to **Voice > Phone numbers**.</span></span> <span data-ttu-id="50d16-172">Atribua números de Conexão de Operador aos usuários usando o Centro de administração do Teams ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50d16-172">Assign Operator Connect numbers to users by using the Teams admin center or by using  PowerShell.</span></span> <span data-ttu-id="50d16-173">Para obter mais informações, consulte [Atribuir números](#assign-numbers).</span><span class="sxs-lookup"><span data-stu-id="50d16-173">For more information, see [Assign numbers](#assign-numbers).</span></span>

   

### <a name="assign-numbers"></a><span data-ttu-id="50d16-174">Atribuir números</span><span class="sxs-lookup"><span data-stu-id="50d16-174">Assign numbers</span></span>

<span data-ttu-id="50d16-175">Se você estiver adicionando novos usuários do Teams ou movendo usuários existentes para o Operator Connect, as etapas para atribuir números são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="50d16-175">Whether you're adding new Teams users or moving existing users to Operator Connect, the steps for assigning numbers are as follows:</span></span>

<span data-ttu-id="50d16-176">Para atribuir números usando o Centro de administração do Teams, vá para **Números de telefone**.</span><span class="sxs-lookup"><span data-stu-id="50d16-176">To assign numbers by using the Teams admin center, go to **Phone numbers**.</span></span> <span data-ttu-id="50d16-177">As etapas são as mesmas que atribuir números para Planos de Chamada.</span><span class="sxs-lookup"><span data-stu-id="50d16-177">The steps are the same as assigning numbers for Calling Plans.</span></span> <span data-ttu-id="50d16-178">Para obter mais informações, [consulte Atribuir um número de telefone a um usuário](assign-change-or-remove-a-phone-number-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="50d16-178">For more information, see [Assign a phone number to a user](assign-change-or-remove-a-phone-number-for-a-user.md).</span></span>

<span data-ttu-id="50d16-179">Para atribuir números usando o PowerShell, use o cmdlet Set-CsOnlineVoiceUser da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="50d16-179">To assign numbers by using PowerShell, use the Set-CsOnlineVoiceUser cmdlet as follows:</span></span>

```
Set-CsOnlineVoiceUser -Identity <user>  -TelephoneNumber <phone number> 
```

<span data-ttu-id="50d16-180">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="50d16-180">For example:</span></span>

```
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

<span data-ttu-id="50d16-181">Para obter mais informações sobre como atribuir números de telefone aos seus usuários, consulte [Atribuir, alterar](assign-change-or-remove-a-phone-number-for-a-user.md)ou remover um número de telefone para um usuário .</span><span class="sxs-lookup"><span data-stu-id="50d16-181">For more information about how to assign phone numbers to your users, see [Assign, change, or remove a phone number for a user](assign-change-or-remove-a-phone-number-for-a-user.md).</span></span>



## <a name="manage-your-operators"></a><span data-ttu-id="50d16-182">Gerenciar seus operadores</span><span class="sxs-lookup"><span data-stu-id="50d16-182">Manage your operators</span></span>

<span data-ttu-id="50d16-183">Na guia Meus operadores, você pode exibir seus operadores e seu status e fazer as seguintes alterações em suas seleções:</span><span class="sxs-lookup"><span data-stu-id="50d16-183">From the My operators tab, you can view your operators and their status and make the following changes to your selections:</span></span>  

- <span data-ttu-id="50d16-184">Gerenciar serviços de operador por país</span><span class="sxs-lookup"><span data-stu-id="50d16-184">Manage operator services by country</span></span>
- <span data-ttu-id="50d16-185">Suspender um operador</span><span class="sxs-lookup"><span data-stu-id="50d16-185">Suspend an operator</span></span>
- <span data-ttu-id="50d16-186">Remover um operador</span><span class="sxs-lookup"><span data-stu-id="50d16-186">Remove an operator</span></span>

> [!NOTE]
> <span data-ttu-id="50d16-187">Antes de remover um operador de sua organização ou de um país, você deve remover todos os números de telefone atribuídos aos usuários na organização ou país e entrar em contato com a operadora para liberar os números.</span><span class="sxs-lookup"><span data-stu-id="50d16-187">Before removing an operator from your organization or from a country, you must remove all phone numbers assigned to users in the organization or country and contact the operator to release the numbers.</span></span>

## <a name="operators"></a><span data-ttu-id="50d16-188">Operadores</span><span class="sxs-lookup"><span data-stu-id="50d16-188">Operators</span></span>

<span data-ttu-id="50d16-189">Você pode adquirir números de telefone das seguintes operadoras, indo para os sites vinculados aqui:</span><span class="sxs-lookup"><span data-stu-id="50d16-189">You can acquire phone numbers from the following operators by going to the websites linked here:</span></span>


|<span data-ttu-id="50d16-190">Operador</span><span class="sxs-lookup"><span data-stu-id="50d16-190">Operator</span></span>  |<span data-ttu-id="50d16-191">Site do operador</span><span class="sxs-lookup"><span data-stu-id="50d16-191">Operator website</span></span>  |
|---------|---------|
|`BT`     |     https://www.globalservices.bt.com/en/aboutus/operator-connect        |
|`Deutsche Telekom`     |   https://cloud.telekom.de/de/blog/cloud-software/microsoft-teams-operator-connect      |
|`Intrado`     | https://insight.intrado.com/operator-connect       |
|`NTT`     |  https://www.hello.global.ntt/operator-connect       |
|`NuWave`     |   https://ipilot.io/microsoft-operator-connect/   |
|`Orange Business Services`     | https://www.orange-business.com/en/blogs/operator-connect-orange-and-microsoft-streamline-calling-for-teams-users        |
|`Pure IP`    | https://info.pure-ip.com/operator-connect        |
|`Rogers`    | https://www.rogers.com/business/products-and-solutions/microsoft-365-business-voice        |
|`TATA Communications`     |  https://www.tatacommunications.com/solutions/unified-communications/unified-communications-as-a-service/microsoft-teams-solutions/       |
|`Telenor`     | https://www.telenor.no/bedrift/telefoni/teams/operator-connect        |
|`Verizon`     |  https://www.verizon.com/business/resources/lp/operator-connect       |
