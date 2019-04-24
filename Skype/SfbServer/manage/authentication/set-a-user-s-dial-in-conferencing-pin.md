---
title: Definir discada um usuário PIN no Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 'Resumo: Defina discada um usuário PIN para Skype para servidor de negócios.'
ms.openlocfilehash: 62b38b8ef15aa2283b66fc18abf5ec0e84e64870
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217898"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a><span data-ttu-id="f9322-103">Definir discada um usuário PIN no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f9322-103">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="f9322-104">**Resumo:** Defina discada um usuário PIN para Skype para servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="f9322-104">**Summary:** Set a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="f9322-105">Para ingressar na conferência discada como usuário autenticado, um Skype para usuário Business Server com credenciais do Active Directory Domain Services (AD DS) requer um número de identificação pessoal (PIN).</span><span class="sxs-lookup"><span data-stu-id="f9322-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="f9322-106">Se um usuário esquece a conferência discada PIN ou não definiu o PIN usando Skype para Business Server, você pode definir o PIN do usuário do Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="f9322-106">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Skype for Business Server, you can set the user's PIN from Skype for Business Server Control Panel.</span></span> <span data-ttu-id="f9322-107">Você pode gerar automaticamente o PIN ou criá-lo manualmente.</span><span class="sxs-lookup"><span data-stu-id="f9322-107">You can automatically generate the PIN or create one manually.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f9322-p102">Características específicas do PIN, como seu tamanho mínimo, podem ser configuradas como uma política. Além da política global, é possível configurar uma política de PIN para sites ou usuários individuais.</span><span class="sxs-lookup"><span data-stu-id="f9322-p102">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy. In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> 
  
### <a name="to-set-a-users-pin"></a><span data-ttu-id="f9322-110">Para definir o PIN de um usuário</span><span class="sxs-lookup"><span data-stu-id="f9322-110">To set a user's PIN</span></span>

1. <span data-ttu-id="f9322-111">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="f9322-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f9322-112">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="f9322-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="f9322-113">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="f9322-113">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="f9322-114">Use um dos seguintes métodos para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="f9322-114">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="f9322-115">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="f9322-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="f9322-116">Se você salvou uma consulta, clique no ícone **Abrir consulta**, use a caixa de diálogo **Abrir** para recuperar a consulta (um arquivo .usf) e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="f9322-116">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="f9322-117">(Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:</span><span class="sxs-lookup"><span data-stu-id="f9322-117">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="f9322-118">a.</span><span class="sxs-lookup"><span data-stu-id="f9322-118">a.</span></span> <span data-ttu-id="f9322-119">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="f9322-119">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="f9322-120">b.</span><span class="sxs-lookup"><span data-stu-id="f9322-120">b.</span></span> <span data-ttu-id="f9322-121">Insira a propriedade do usuário digitando ou clicando na seta da lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="f9322-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="f9322-122">c.</span><span class="sxs-lookup"><span data-stu-id="f9322-122">c.</span></span> <span data-ttu-id="f9322-123">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="f9322-123">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="f9322-124">d.</span><span class="sxs-lookup"><span data-stu-id="f9322-124">d.</span></span> <span data-ttu-id="f9322-125">Dependendo da propriedade de usuário selecionada, insira os critérios que você deseja usar para filtrar os resultados da pesquisa digitando-os ou clicando na seta da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="f9322-125">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="f9322-126">Para adicionar cláusulas de pesquisa adicionais à sua consulta, clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="f9322-126">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="f9322-127">f.</span><span class="sxs-lookup"><span data-stu-id="f9322-127">e.</span></span> <span data-ttu-id="f9322-128">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="f9322-128">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f9322-p108">Se o PIN estiver bloqueado, você deverá desbloqueá-lo para poder defini-lo. Para desbloquear o PIN, clique no usuário, clique em **Ação** e depois em **Desbloquear PIN**.</span><span class="sxs-lookup"><span data-stu-id="f9322-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="f9322-131">Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em **Definir PIN**.</span><span class="sxs-lookup"><span data-stu-id="f9322-131">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>
    
7. <span data-ttu-id="f9322-132">Na caixa de diálogo **Definir PIN**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="f9322-132">In the **Set PIN** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="f9322-133">Para permitir que Skype para Business Server gere o PIN do usuário, selecione **Gerar automaticamente um PIN válido** (padrão).</span><span class="sxs-lookup"><span data-stu-id="f9322-133">To allow Skype for Business Server to generate the user's PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
   - <span data-ttu-id="f9322-134">Para criar seu próprio PIN, clique em **Inserir manualmente um PIN específico**, clique na caixa de texto e digite um PIN na caixa de texto que atenda aos requisitos de PIN especificados nas configurações de política de PIN.</span><span class="sxs-lookup"><span data-stu-id="f9322-134">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>
    
8. <span data-ttu-id="f9322-135">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9322-135">Click **OK**.</span></span>
    
9. <span data-ttu-id="f9322-136">Em **Definir PIN**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="f9322-136">In **Set PIN**, do one of the following:</span></span> 
    
   - <span data-ttu-id="f9322-137">Marque a caixa de seleção **Mostrar PIN** para ver o PIN e copie o PIN e comunique-o ao usuário usando o método preferencial da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f9322-137">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
   - <span data-ttu-id="f9322-p109">Clique em **Abrir meu aplicativo de email para enviar o novo PIN para o usuário** para enviar o novo PIN por email. Se o Microsoft Office Outlook for seu cliente de email, o PIN será copiado automaticamente para uma nova mensagem de email. Se você usar um cliente de email diferente, marque a caixa de seleção **Mostrar PIN** para ver o PIN e copiá-lo em sua mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="f9322-p109">Click **Open my email application to send the new PIN to the user** to send the PIN by email. If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message. If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>
    
10. <span data-ttu-id="f9322-141">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="f9322-141">Click **Close**.</span></span>
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f9322-142">Atribuindo um PIN de usuário usando Cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9322-142">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f9322-143">Você pode atribuir números PIN utilizando o cmdlet Set-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="f9322-143">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="f9322-144">Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9322-144">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f9322-145">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="f9322-145">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="f9322-146">O processo é o mesmo em Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="f9322-146">The process is the same in Skype for Business Server.</span></span> 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="f9322-147">Para atribuir automaticamente um número PIN a um usuário</span><span class="sxs-lookup"><span data-stu-id="f9322-147">To auto-assign a PIN number to a user</span></span>

<span data-ttu-id="f9322-148">O comando a seguir atribui um número PIN ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="f9322-148">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="f9322-149">Porque o parâmetro Pin não for incluído, Skype para Business Server irá gerar automaticamente e atribuir o número PIN.</span><span class="sxs-lookup"><span data-stu-id="f9322-149">Because the Pin parameter is not included, Skype for Business Server will automatically generate and assign the PIN number.</span></span>
    
  ```
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="f9322-150">Para atribuir um número PIN específico a um usuário</span><span class="sxs-lookup"><span data-stu-id="f9322-150">To assign a specific PIN number to a user</span></span>

<span data-ttu-id="f9322-151">Esse comando utiliza o parâmetro PIN para atribuir o número de PIN 121989 ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="f9322-151">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
  ```
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

<span data-ttu-id="f9322-152">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f9322-152">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) cmdlet.</span></span>
  

