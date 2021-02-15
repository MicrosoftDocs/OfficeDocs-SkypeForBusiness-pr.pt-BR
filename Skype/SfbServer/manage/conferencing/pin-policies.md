---
title: Gerenciar políticas de PIN para conferência discada no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 'Resumo: Saiba como gerenciar políticas de PIN para conferência discada no Skype for Business Server.'
ms.openlocfilehash: 6544586071f1107537232a117de196dfbffeb4aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827947"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="a66e7-103">Gerenciar políticas de PIN para conferência discada no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a66e7-103">Manage PIN policies for dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="a66e7-104">**Resumo:** Saiba como gerenciar políticas de PIN para conferência discada no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a66e7-104">**Summary:** Learn how to manage PIN policies for dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="a66e7-105">Os usuários do Skype for Business Server que têm credenciais do AD DS (Serviços de Domínio Active Directory) em sua organização podem ingressar em conferências discadas como usuários autenticados usando um PIN (número de identificação pessoal).</span><span class="sxs-lookup"><span data-stu-id="a66e7-105">Skype for Business Server users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="a66e7-106">A política de PIN define as regras de funcionamento dos PINs de conferências de discagem.</span><span class="sxs-lookup"><span data-stu-id="a66e7-106">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>
  
 <span data-ttu-id="a66e7-107">Se você quiser usar a mesma política de PIN para toda sua organização, poderá usar a política de PIN global e modificá-la conforme o necessário.</span><span class="sxs-lookup"><span data-stu-id="a66e7-107">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed.</span></span> <span data-ttu-id="a66e7-108">A política de PIN global define as regras para PINs de conferências de discagem no nível da floresta.</span><span class="sxs-lookup"><span data-stu-id="a66e7-108">The global PIN policy defines the rules for dial-in conferencing PINs at the forest level.</span></span> <span data-ttu-id="a66e7-109">Você pode modificar a política de PIN global, mas não pode excluí-la.</span><span class="sxs-lookup"><span data-stu-id="a66e7-109">You can modify the global PIN policy, but you cannot delete it.</span></span>
  
<span data-ttu-id="a66e7-110">É possível criar uma nova política de PIN se você quiser que uma política específica seja aplicada a um site ou a determinado grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="a66e7-110">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span>
  
<span data-ttu-id="a66e7-111">As políticas de PIN se aplicam aos usuários a partir do escopo mais estreito para o mais amplo.</span><span class="sxs-lookup"><span data-stu-id="a66e7-111">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="a66e7-112">Se você atribuir uma política de PIN no nível de usuário a um usuário, essas configurações terão precedência.</span><span class="sxs-lookup"><span data-stu-id="a66e7-112">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="a66e7-113">Se você não atribuir uma política de usuário, a política de PIN no nível de site será aplicada, se existir.</span><span class="sxs-lookup"><span data-stu-id="a66e7-113">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="a66e7-114">Se nenhuma política de usuário ou site se aplicar, a política de PIN global fornecerá as configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="a66e7-114">If no user or site policies apply, global PIN policy provides the default settings.</span></span>
  
## <a name="view-information-about-pin-policies"></a><span data-ttu-id="a66e7-115">Exibir informações sobre políticas de PIN</span><span class="sxs-lookup"><span data-stu-id="a66e7-115">View information about PIN policies</span></span>

<span data-ttu-id="a66e7-116">Você pode exibir informações sobre políticas de PIN usando o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a66e7-116">You can view information about PIN policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a66e7-117">Exibir informações sobre políticas de PIN usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a66e7-117">View information about PIN policies by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="a66e7-118">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a66e7-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="a66e7-119">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a66e7-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a66e7-120">Na barra de navegação esquerda, clique em **Conferência** e **Política de PIN**.</span><span class="sxs-lookup"><span data-stu-id="a66e7-120">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="a66e7-121">Na página **Política de PIN,** clique na política de PIN que você deseja exibir, clique em **Editar** e em **Mostrar detalhes.**</span><span class="sxs-lookup"><span data-stu-id="a66e7-121">On the **PIN Policy** page, click the PIN policy that you want to view, click **Edit**, and then click **Show details**.</span></span>
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a66e7-122">Exibir informações sobre políticas de PIN usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a66e7-122">View information about PIN policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="a66e7-123">Para exibir informações sobre políticas de PIN, use o cmdlet **Get-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="a66e7-123">To view information about PIN policies, use the **Get-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="a66e7-124">Por exemplo, o comando a seguir retorna informações sobre uma única política de PIN com a Identidade site:Redmond:</span><span class="sxs-lookup"><span data-stu-id="a66e7-124">For example, the following command returns information about a single PIN policy with the Identity site:Redmond:</span></span>
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

<span data-ttu-id="a66e7-125">Para obter mais informações, incluindo uma descrição de sintaxe completa e uma lista de parâmetros, consulte [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="a66e7-125">For more information, including a complete syntax description and list of parameters, see [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-the-global-pin-policy"></a><span data-ttu-id="a66e7-126">Modificar a política de PIN global</span><span class="sxs-lookup"><span data-stu-id="a66e7-126">Modify the global PIN policy</span></span>

<span data-ttu-id="a66e7-127">Você pode modificar a política de PIN global usando o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a66e7-127">You can modify the global PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a66e7-128">Modificar a política de PIN de conferência discada global usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a66e7-128">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="a66e7-129">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a66e7-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="a66e7-130">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a66e7-130">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a66e7-131">Na barra de navegação esquerda, clique em **Conferência** e **Política de PIN**.</span><span class="sxs-lookup"><span data-stu-id="a66e7-131">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="a66e7-132">Na página **Política de PIN**, clique na política **Global**, em **Editar** e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="a66e7-132">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="a66e7-p105">Em **Editar Política de PIN**, em **Tamanho mínimo do PIN**, digite ou selecione o tamanho mínimo do PIN que você deseja permitir. O tamanho mínimo padrão é de cinco dígitos.</span><span class="sxs-lookup"><span data-stu-id="a66e7-p105">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="a66e7-p106">Para poder especificar o número máximo de tentativas de logon antes que um usuário seja bloqueado, marque a caixa de seleção **Especificar o máximo de tentativas de logon** . Se você não selecionar essa opção, o número máximo de tentativas permitidas será determinado automaticamente com base no tamanho do PIN. Por padrão, o número máximo de tentativas é determinado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a66e7-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="a66e7-138">Se você marcou a caixa de seleção **Especificar o máximo de tentativas de logon**, em **Máximo de tentativas de logon**, digite ou selecione o número máximo de tentativas de logon que você deseja permitir.</span><span class="sxs-lookup"><span data-stu-id="a66e7-138">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="a66e7-p107">Para fazer com que os PINs expirem, marque a caixa de seleção **Habilitar validade do PIN**. Se você não selecionar essa opção, os PINs nunca expirarão. Por padrão, os PINs nunca expiram.</span><span class="sxs-lookup"><span data-stu-id="a66e7-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="a66e7-142">Se você marcou a caixa de seleção **Habilitar validade do PIN**, em **O PIN expira após (dias)**, digite ou selecione o número de dias após o qual o PIN expirará.</span><span class="sxs-lookup"><span data-stu-id="a66e7-142">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="a66e7-p108">Em **Contagem do histórico de PINs**, digite o número de PINs que um usuário precisa criar antes de poder reutilizar um PIN. Por padrão, os usuários podem reutilizar seus PINs.</span><span class="sxs-lookup"><span data-stu-id="a66e7-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="a66e7-p109">Para permitir padrões comuns de dígitos nos PINs, como números sequenciais e conjuntos repetitivos de números, marque a caixa de seleção **Permitir padrões comuns**. Se você não selecionar essa opção, somente os padrões complexos de dígitos serão permitidos. Por padrão, somente os padrões complexos de dígitos são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a66e7-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a66e7-148">Por motivos de segurança, a Microsoft recomenda que você não permita padrões comuns.</span><span class="sxs-lookup"><span data-stu-id="a66e7-148">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="a66e7-149">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a66e7-149">Click **Commit**.</span></span>
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a66e7-150">Modificar a política de PIN de conferência discada global usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a66e7-150">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="a66e7-151">Para modificar a política de PIN de conferência discada global, use o cmdlet **Set-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="a66e7-151">To modify the global dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="a66e7-152">O comando a seguir altera o valor de MinPasswordLength para todas as políticas de PIN configuradas para uso na organização.</span><span class="sxs-lookup"><span data-stu-id="a66e7-152">The following command changes the value of the MinPasswordLength for all the PIN policies configured for use in the organization.</span></span> <span data-ttu-id="a66e7-153">Para fazer isso, o comando primeiro chama o cmdlet **Get-CsPinPolicy** sem nenhum parâmetro para recuperar uma coleção de todas as políticas de PIN existentes.</span><span class="sxs-lookup"><span data-stu-id="a66e7-153">To do this, the command first calls the **Get-CsPinPolicy** cmdlet without any parameters in order to retrieve a collection of all the existing PIN policies.</span></span> <span data-ttu-id="a66e7-154">Essa coleção será então canalizada para o cmdlet **Set-CsPinPolicy,** que modificará o valor da propriedade MinPasswordLength de cada diretiva na coleção:</span><span class="sxs-lookup"><span data-stu-id="a66e7-154">That collection is then piped to the **Set-CsPinPolicy** cmdlet, which modifies the value of the MinPasswordLength property for each policy in the collection:</span></span>
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

<span data-ttu-id="a66e7-155">Para obter mais informações, incluindo uma descrição de sintaxe completa e uma lista de parâmetros, consulte [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="a66e7-155">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="create-a-user-or-site-pin-policy"></a><span data-ttu-id="a66e7-156">Criar uma política de PIN de site ou usuário</span><span class="sxs-lookup"><span data-stu-id="a66e7-156">Create a user or site PIN policy</span></span>

<span data-ttu-id="a66e7-157">Você pode criar uma política de PIN de site ou usuário usando o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a66e7-157">You can create a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a66e7-158">Criar uma política de PIN de site ou usuário usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a66e7-158">Create a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a66e7-159">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a66e7-159">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="a66e7-160">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a66e7-160">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a66e7-161">Na barra de navegação esquerda, clique em **Conferência** e **Política de PIN**.</span><span class="sxs-lookup"><span data-stu-id="a66e7-161">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="a66e7-162">Na página **Política de PIN**, clique em **Novo** e execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="a66e7-162">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="a66e7-p111">Para criar uma política de nível de usuário, clique em **Política de usuário**. Em **Nova Política de PIN**, em **Nome**, digite um nome que descreve a política.</span><span class="sxs-lookup"><span data-stu-id="a66e7-p111">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="a66e7-p112">Para criar uma política de nível de site, clique em **Política de site**. No campo de pesquisa **Selecionar um Site**, digite todo ou parte do nome do site para o qual você deseja criar uma política. Na lista de sites, clique no site que você deseja e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a66e7-p112">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="a66e7-168">No campo **Descrição**, digite uma descrição da política de PIN.</span><span class="sxs-lookup"><span data-stu-id="a66e7-168">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="a66e7-p113">No campo **Tamanho mínimo do PIN**, digite ou selecione o tamanho mínimo do PIN que você deseja permitir. O tamanho mínimo padrão é de cinco dígitos.</span><span class="sxs-lookup"><span data-stu-id="a66e7-p113">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="a66e7-p114">Para poder especificar o número máximo de tentativas de logon antes que um usuário seja bloqueado, marque a caixa de seleção **Especificar o máximo de tentativas de logon** . Se você não selecionar essa opção, o número máximo de tentativas permitidas será determinado automaticamente com base no tamanho do PIN. Por padrão, o número máximo de tentativas é determinado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a66e7-p114">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="a66e7-174">Se você marcou a caixa de seleção **Especificar o máximo de tentativas de logon**, em **Máximo de tentativas de logon**, digite ou selecione o número máximo de tentativas de logon que você deseja permitir.</span><span class="sxs-lookup"><span data-stu-id="a66e7-174">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="a66e7-p115">Para fazer com que os PINs expirem, marque a caixa de seleção **Habilitar validade do PIN**. Se você não selecionar essa opção, os PINs nunca expirarão. Por padrão, os PINs nunca expiram.</span><span class="sxs-lookup"><span data-stu-id="a66e7-p115">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="a66e7-178">Se você marcou a caixa de seleção **Habilitar validade do PIN**, em **O PIN expira após (dias)**, digite ou selecione o número de dias após o qual o PIN expirará.</span><span class="sxs-lookup"><span data-stu-id="a66e7-178">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="a66e7-p116">Em **Contagem do histórico de PINs**, digite o número de PINs que um usuário precisa criar antes de poder reutilizar um PIN. Por padrão, os usuários podem reutilizar seus PINs.</span><span class="sxs-lookup"><span data-stu-id="a66e7-p116">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="a66e7-p117">Para permitir padrões comuns de dígitos nos PINs, como números sequenciais e conjuntos repetitivos de números, marque a caixa de seleção **Permitir padrões comuns**. Se você não selecionar essa opção, somente os padrões complexos de dígitos serão permitidos. Por padrão, somente os padrões complexos de dígitos são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a66e7-p117">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a66e7-184">Por motivos de segurança, a Microsoft recomenda que você não permita padrões comuns.</span><span class="sxs-lookup"><span data-stu-id="a66e7-184">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="a66e7-185">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a66e7-185">Click **Commit**.</span></span>
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a66e7-186">Criar uma política de PIN de site ou usuário usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a66e7-186">Create a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="a66e7-187">Para criar uma política de PIN de site ou usuário, use o cmdlet **New-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="a66e7-187">To create a user or site PIN policy, use the **New-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="a66e7-188">O comando a seguir cria uma nova política de PIN com a Identidade site:Redmond.</span><span class="sxs-lookup"><span data-stu-id="a66e7-188">The following command creates a new PIN policy with the Identity site:Redmond.</span></span> <span data-ttu-id="a66e7-189">Esse comando inclui apenas um parâmetro opcional, MinPasswordLength, que é usado para definir a propriedade MinPasswordLength como 7.</span><span class="sxs-lookup"><span data-stu-id="a66e7-189">This command includes just one optional parameter, MinPasswordLength, which is used to set the MinPasswordLength property to 7.</span></span> <span data-ttu-id="a66e7-190">Todas as demais propriedades de política serão configuradas usando-se os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="a66e7-190">All the remaining policy properties will be configured using the default values.</span></span>
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 <span data-ttu-id="a66e7-191">Para obter mais informações, incluindo uma descrição de sintaxe completa e uma lista de parâmetros, consulte [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="a66e7-191">For more information, including a complete syntax description and list of parameters, see [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-a-user-or-site-pin-policy"></a><span data-ttu-id="a66e7-192">Modificar uma política de PIN de site ou usuário</span><span class="sxs-lookup"><span data-stu-id="a66e7-192">Modify a user or site PIN policy</span></span>

<span data-ttu-id="a66e7-193">Você pode modificar uma política de PIN de site ou usuário usando o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a66e7-193">You can modify a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a66e7-194">Modificar uma política de PIN de site ou usuário usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a66e7-194">Modify a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="a66e7-195">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a66e7-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="a66e7-196">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a66e7-196">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a66e7-197">Na barra de navegação esquerda, clique em **Conferência** e **Política de PIN**.</span><span class="sxs-lookup"><span data-stu-id="a66e7-197">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="a66e7-198">Na página **Política de PIN**, clique na política de PIN que você deseja alterar, clique em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="a66e7-198">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="a66e7-199">Em **Editar Política de PIN**, modifique quaisquer configurações de política (exceto o nome da política, que não pode ser modificado).</span><span class="sxs-lookup"><span data-stu-id="a66e7-199">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>
    
6. <span data-ttu-id="a66e7-200">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a66e7-200">Click **Commit**.</span></span>
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a66e7-201">Modificar uma política de PIN de site ou usuário usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a66e7-201">Modify a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="a66e7-202">Para modificar a política de PIN de conferência discada, use o cmdlet **Set-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="a66e7-202">To modify the dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="a66e7-203">O comando a seguir modifica a política de PIN atribuída ao site Redmond.</span><span class="sxs-lookup"><span data-stu-id="a66e7-203">The following command modifies the PIN policy assigned to the Redmond site.</span></span> <span data-ttu-id="a66e7-204">Nesse caso, o comando altera o valor da propriedade MinPasswordLength para 10; Isso significa que os novos PINs terão que conter pelo menos 10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="a66e7-204">In this case, the command changes the value of the MinPasswordLength property to 10; that means that new PINs will have to contain at least 10 digits:</span></span>
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

<span data-ttu-id="a66e7-205">Para obter mais informações, incluindo uma descrição de sintaxe completa e uma lista de parâmetros, consulte [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="a66e7-205">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="delete-a-user-or-site-pin-policy"></a><span data-ttu-id="a66e7-206">Excluir uma política de PIN de site ou usuário</span><span class="sxs-lookup"><span data-stu-id="a66e7-206">Delete a user or site PIN policy</span></span>

<span data-ttu-id="a66e7-207">Você pode excluir uma política de PIN de site ou usuário usando o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a66e7-207">You can delete a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a66e7-208">Excluir uma política de PIN de site ou usuário usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a66e7-208">Delete a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="a66e7-209">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a66e7-209">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="a66e7-210">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a66e7-210">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a66e7-211">Na barra de navegação esquerda, clique em **Conferência** e **Política de PIN**.</span><span class="sxs-lookup"><span data-stu-id="a66e7-211">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="a66e7-212">Na página **Política de PIN,** clique na política de PIN que você deseja alterar, clique em **Editar** e em **Excluir.**</span><span class="sxs-lookup"><span data-stu-id="a66e7-212">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Delete**.</span></span>
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a66e7-213">Excluir uma política de PIN de site ou usuário usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a66e7-213">Delete a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="a66e7-214">Para excluir uma política de PIN de site ou usuário, use o cmdlet **Remove-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="a66e7-214">To delete a user or site PIN policy, use the **Remove-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="a66e7-215">O comando a seguir remove todas as políticas de PIN que foram configuradas no escopo do site.</span><span class="sxs-lookup"><span data-stu-id="a66e7-215">The following command removes all the PIN policies that have been configured at the site scope.</span></span> <span data-ttu-id="a66e7-216">Para fazer isso, use o cmdlet **Get-CsPinPolicy,** juntamente com o parâmetro Filter, para retornar uma coleção de todas as políticas que tenham uma Identidade que comece com os caracteres "site:".</span><span class="sxs-lookup"><span data-stu-id="a66e7-216">To do this, use the **Get-CsPinPolicy** cmdlet, along with the Filter parameter, to return a collection of all the policies that have an Identity that begins with the characters "site:".</span></span> <span data-ttu-id="a66e7-217">Esta coleção será então canalada para o cmdlet **Remove-CsPinPolicy,** que excluirá cada política na coleção:</span><span class="sxs-lookup"><span data-stu-id="a66e7-217">This collection is then piped to the **Remove-CsPinPolicy** cmdlet, which deletes each policy in the collection:</span></span>
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

<span data-ttu-id="a66e7-218">Para obter mais informações, incluindo uma descrição de sintaxe completa e uma lista de parâmetros, [consulte Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="a66e7-218">For more information, including a complete syntax description and list of parameters, see [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span></span>
  

