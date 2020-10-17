---
title: 'Lync Server 2013: definir PIN de conferência discada de um usuário'
description: 'Lync Server 2013: definir PIN de conferência discada de um usuário.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 238c2a72da81a53b409d81c1b91c885f1ddabcbc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543327"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a><span data-ttu-id="f5a17-103">Definir PIN de conferência discada de um usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5a17-103">Set a user's dial-in conferencing PIN in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5a17-104">_**Última modificação do tópico:** 2014-06-10_</span><span class="sxs-lookup"><span data-stu-id="f5a17-104">_**Topic Last Modified:** 2014-06-10_</span></span>

<span data-ttu-id="f5a17-105">Para ingressar em uma conferência discada como um usuário autenticado, um usuário do Lync Server 2013 com credenciais do AD DS (serviços de domínio Active Directory) requer um PIN (número de identificação pessoal).</span><span class="sxs-lookup"><span data-stu-id="f5a17-105">To join a dial-in conference as an authenticated user, a Lync Server 2013 user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="f5a17-106">Se um usuário esquecer o PIN de conferência discada ou não tiver definido o PIN usando o Lync Server, você poderá definir o PIN do usuário no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f5a17-106">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Lync Server, you can set the user’s PIN from Lync Server Control Panel.</span></span> <span data-ttu-id="f5a17-107">Você pode gerar automaticamente o PIN ou criá-lo manualmente.</span><span class="sxs-lookup"><span data-stu-id="f5a17-107">You can automatically generate the PIN or create one manually.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f5a17-108">Características específicas do PIN, como seu tamanho mínimo, podem ser configuradas como uma política.</span><span class="sxs-lookup"><span data-stu-id="f5a17-108">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy.</span></span> <span data-ttu-id="f5a17-109">Além da política global, é possível configurar uma política de PIN para sites ou usuários individuais.</span><span class="sxs-lookup"><span data-stu-id="f5a17-109">In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> <span data-ttu-id="f5a17-110">Para obter detalhes sobre como configurar uma política de PIN, consulte <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">configurar regras de PIN (número de identificação pessoal) de conferência discada no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f5a17-110">For details about configuring a PIN policy, see <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-set-a-users-pin"></a><span data-ttu-id="f5a17-111">Para definir o PIN de um usuário</span><span class="sxs-lookup"><span data-stu-id="f5a17-111">To set a user’s PIN</span></span>

1.  <span data-ttu-id="f5a17-112">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="f5a17-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f5a17-113">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f5a17-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f5a17-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f5a17-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f5a17-115">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="f5a17-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="f5a17-116">Utilize um dos métodos a seguir para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="f5a17-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="f5a17-117">Na caixa **Buscar usuários**, digite toda ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta do Gerenciador de Contas de Segurança (SAM), endereço SIP ou linha do Uniform Resource Identifier (URI) da conta de usuário, e então clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="f5a17-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="f5a17-118">Se você tiver uma consulta salva, clique no ícone **Abrir consulta**, utilize a caixa de diálogo **Abrir**  para obter a consulta (um arquivo .usf) e, então, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="f5a17-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="f5a17-119">(Opcional) Especifique critérios de busca adicionais para limitar os resultados:</span><span class="sxs-lookup"><span data-stu-id="f5a17-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="f5a17-120">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="f5a17-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="f5a17-121">Insira a propriedade de usuário digitando ou clicando na seta na lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="f5a17-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="f5a17-122">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="f5a17-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="f5a17-123">Dependendo da propriedade de usuário selecionada, insira o critério que deseja utilizar para filtrar os resultados da busca digitando ou clicando na seta na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="f5a17-123">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="f5a17-124">Para adicionar cláusulas de pesquisa à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f5a17-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="f5a17-125">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="f5a17-125">Click **Find**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f5a17-p104">Se o PIN estiver bloqueado, você deverá desbloquear o PIN para que possa defini-lo. Para desbloquear o PIN, clique no usuário, clique em <STRONG>Ação</STRONG> e em <STRONG>Desbloquear PIN</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f5a17-p104">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click <STRONG>Action</STRONG>, and then click <STRONG>Unlock PIN</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="f5a17-128">Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em **Definir PIN**.</span><span class="sxs-lookup"><span data-stu-id="f5a17-128">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>

7.  <span data-ttu-id="f5a17-129">Na caixa de diálogo **Definir PIN**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="f5a17-129">In the **Set PIN** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="f5a17-130">Para permitir que o Lync Server 2013 gere o PIN do usuário, selecione **gerar automaticamente um PIN válido** (padrão).</span><span class="sxs-lookup"><span data-stu-id="f5a17-130">To allow Lync Server 2013 to generate the user’s PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
      - <span data-ttu-id="f5a17-131">Para criar seu próprio PIN, clique em **Inserir manualmente um PIN específico**, clique na caixa de texto e digite um PIN na caixa de texto que atenda aos requisitos de PIN especificados nas configurações de política de PIN.</span><span class="sxs-lookup"><span data-stu-id="f5a17-131">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>

8.  <span data-ttu-id="f5a17-132">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5a17-132">Click **OK**.</span></span>

9.  <span data-ttu-id="f5a17-133">Em **Definir PIN**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="f5a17-133">In **Set PIN**, do one of the following:</span></span>
    
      - <span data-ttu-id="f5a17-134">Marque a caixa de seleção **Mostrar PIN** para ver o PIN e copie o PIN e comunique-o ao usuário usando o método preferencial da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f5a17-134">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
      - <span data-ttu-id="f5a17-p105">Clique em **Abrir meu aplicativo de email para enviar o novo PIN para o usuário** para enviar o novo PIN por email. Se o Microsoft Office Outlook for seu cliente de email, o PIN será copiado automaticamente para uma nova mensagem de email. Se você usar um cliente de email diferente, marque a caixa de seleção **Mostrar PIN** para ver o PIN e copiá-lo em sua mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="f5a17-p105">Click **Open my email application to send the new PIN to the user** to send the PIN by email. If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message. If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>

10. <span data-ttu-id="f5a17-138">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="f5a17-138">Click **Close**.</span></span>

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f5a17-139">Atribuindo um PIN do usuário usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5a17-139">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f5a17-140">Você pode atribuir números de PIN que também podem ser atribuídos usando o cmdlet Set-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="f5a17-140">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="f5a17-141">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5a17-141">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f5a17-142">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="f5a17-142">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="f5a17-143">Para atribuir automaticamente um número PIN a um usuário</span><span class="sxs-lookup"><span data-stu-id="f5a17-143">To auto-assign a PIN number to a user</span></span>

  - <span data-ttu-id="f5a17-144">O comando a seguir atribui um número PIN ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="f5a17-144">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="f5a17-145">Como o parâmetro PIN não está incluído, o Lync Server gerará e atribuirá automaticamente o número do PIN.</span><span class="sxs-lookup"><span data-stu-id="f5a17-145">Because the Pin parameter is not included, Lync Server will automatically generate and assign the PIN number.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="f5a17-146">Para atribuir um número de PIN específico a um usuário</span><span class="sxs-lookup"><span data-stu-id="f5a17-146">To assign a specific PIN number to a user</span></span>

  - <span data-ttu-id="f5a17-147">Esse comando utiliza o parâmetro PIN para atribuir o número de PIN 121989 ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="f5a17-147">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

<span data-ttu-id="f5a17-148">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) .</span><span class="sxs-lookup"><span data-stu-id="f5a17-148">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f5a17-149">Confira também</span><span class="sxs-lookup"><span data-stu-id="f5a17-149">See Also</span></span>


<span data-ttu-id="f5a17-150">[Número de Acesso de Discagem](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f5a17-150">[Dial-in Access Number](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))</span></span>  


[<span data-ttu-id="f5a17-151">Configurar regras de PIN (número de identificação pessoal) de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5a17-151">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

