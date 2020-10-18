---
title: Criar ou modificar um conjunto de definições de configuração de reunião
description: Criar ou modificar um conjunto de definições de configuração de reunião.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of meeting configuration settings
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49733822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51dd68b3d149e5a96628fc3343d0d7eb3ae8020d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578237"
---
# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="436c2-103">Criar ou modificar um conjunto de definições de configuração de reunião no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="436c2-103">Create or modify a collection of meeting configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="436c2-104">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="436c2-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="436c2-p101">É possível usar as configurações na página Configuração da Reunião para definir várias características da experiência de participação da reunião. Por padrão, as configurações globais definem a experiência de participação. Você também pode criar configurações de participação de reuniões a nível local e a nível de pool. Se você criar configurações a nível de pool, elas se aplicarão a todas as reuniões hospedadas pelo pool. Se você não criar configurações a nível de pool, as configurações a nível local serão aplicadas, caso existam. Se você não definir as configurações a nível local, as configurações globais serão aplicadas a todas as reuniões.</span><span class="sxs-lookup"><span data-stu-id="436c2-p101">You can use the settings on the Meeting Configuration page to define various characteristics of the meeting join experience. By default, the global settings define the join experience. You can also create site-level and pool-level meeting join settings. If you create pool-level settings, those settings apply to all meetings hosted by that pool. If you do not create pool-level settings, site-level settings apply, if they exist. If you do not define site-level settings, the global settings apply to all meetings.</span></span>

<div>

## <a name="to-create-new-meeting-join-settings"></a><span data-ttu-id="436c2-111">Para criar novas configurações de participação de reunião</span><span class="sxs-lookup"><span data-stu-id="436c2-111">To create new meeting join settings</span></span>

1.  <span data-ttu-id="436c2-112">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="436c2-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="436c2-113">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="436c2-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="436c2-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="436c2-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="436c2-115">Na barra de navegação esquerda, clique em **Conferência** e em **Configuração da reunião**.</span><span class="sxs-lookup"><span data-stu-id="436c2-115">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="436c2-116">Na página \*\*Configuração de reunião \*\*, clique em \*\*Novo \*\* e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="436c2-116">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="436c2-p103">Para criar uma política a nível local, clique em **Configuração local**. No campo de pesquisa **Selecionar um local**, digite todo ou parte do nome do local para o qual você deseja definir as configurações de participação de reunião. Na lista resultante de locais, clique no local desejado e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="436c2-p103">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="436c2-p104">Para criar uma política a nível de pool, clique em **Configuração do pool**. No campo de pesquisa **Selecionar um serviço**, digite todo ou parte do nome do serviço do pool para o qual você deseja definir as configurações de participação de reunião. Na lista resultante de serviços, clique no pool desejado e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="436c2-p104">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="436c2-p105">Para direcionar os participantes que ligam por um PSTN através do lobby, desmarque a caixa de seleção **Os chamadores PSTN ignoram o lobby**. Por padrão, os participantes discando pelo PSTN vão diretamente para a reunião.</span><span class="sxs-lookup"><span data-stu-id="436c2-p105">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>

6.  <span data-ttu-id="436c2-125">Para configurar quem pode ser um apresentador na reunião, em **Designar como apresentador**, faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="436c2-125">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
      - <span data-ttu-id="436c2-126">Para não permitir que qualquer pessoa além do organizador seja o apresentador, clique em **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="436c2-126">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
      - <span data-ttu-id="436c2-p106">Para permitir que apenas participantes membros da sua organização sejam apresentadores, clique em **Empresa**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="436c2-p106">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
      - <span data-ttu-id="436c2-129">Para permitir qualquer participante ser o apresentador, clique em **Todos**.</span><span class="sxs-lookup"><span data-stu-id="436c2-129">To allow any participants to be a presenter, click **Everyone**.</span></span>

7.  <span data-ttu-id="436c2-p107">Para que o organizador selecione um tipo de conferência ao programar uma reunião, desmarque a caixa de seleção **Tipo de conferência atribuída por padrão**. Por padrão, o tipo de conferência é atribuído automaticamente.</span><span class="sxs-lookup"><span data-stu-id="436c2-p107">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>

8.  <span data-ttu-id="436c2-p108">Para evitar que usuários anônimos (não autenticados) sejam aceitos automaticamente, desmarque a caixa de seleção **Aceitar usuários anônimos por padrão**. Por padrão, os usuários anônimos são aceitos automaticamente nas reuniões.</span><span class="sxs-lookup"><span data-stu-id="436c2-p108">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>

9.  <span data-ttu-id="436c2-134">Para personalizar o convite da reunião enviado para os participantes, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="436c2-134">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="436c2-135">Observe que o comprimento máximo das URLs e o texto do rodapé padrão é de 1KB.</span><span class="sxs-lookup"><span data-stu-id="436c2-135">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="436c2-136">Exceto para a **URL de ajuda**, se você não especificar um valor para as personalizações, não serão incluídas na reunião.</span><span class="sxs-lookup"><span data-stu-id="436c2-136">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="436c2-137">Se você não incluir uma URL de ajuda personalizada, a URL de ajuda padrão para o Lync será exibida no convite.</span><span class="sxs-lookup"><span data-stu-id="436c2-137">If you do not include a custom help URL, the default help URL for Lync will be displayed in the invite.</span></span>
    
      - <span data-ttu-id="436c2-138">Para personalizar o logotipo exibido no convite da reunião, em **URL do logotipo**, insira o local do logotipo.</span><span class="sxs-lookup"><span data-stu-id="436c2-138">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="436c2-139">O logotipo deve ser uma imagem GIF ou JPG com um tamanho de 188 por 30 pixels.</span><span class="sxs-lookup"><span data-stu-id="436c2-139">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span>

        
        </div>
    
      - <span data-ttu-id="436c2-140">Para personalizar o texto de ajuda exibido no convite da reunião, na **URL de ajuda**, insira o local do texto de ajuda.</span><span class="sxs-lookup"><span data-stu-id="436c2-140">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
      - <span data-ttu-id="436c2-141">Para personalizar o texto legal exibido no convite da reunião, na **URL do texto legal**, insira o local do logotipo.</span><span class="sxs-lookup"><span data-stu-id="436c2-141">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
      - <span data-ttu-id="436c2-142">Para personalizar o texto do rodapé exibido no convite da reunião, em **Texto do rodapé personalizado**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="436c2-142">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>

10. <span data-ttu-id="436c2-143">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="436c2-143">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a><span data-ttu-id="436c2-144">Para modificar um conjunto existente de configurações de reunião</span><span class="sxs-lookup"><span data-stu-id="436c2-144">To modify an existing collection of meeting configurations</span></span>

1.  <span data-ttu-id="436c2-145">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="436c2-145">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="436c2-146">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="436c2-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="436c2-147">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="436c2-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="436c2-148">Na barra de navegação esquerda, clique em **Conferência** e em **Configuração da reunião**.</span><span class="sxs-lookup"><span data-stu-id="436c2-148">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="436c2-149">Na lista de configurações de reunião, clique na configuração que deseja alterar, clique em **Editar**e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="436c2-149">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="436c2-150">Em **Editar configuração de reunião**, modifique qualquer definição da configuração, exceto o nome da configuração, que não pode ser modificado.</span><span class="sxs-lookup"><span data-stu-id="436c2-150">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>

6.  <span data-ttu-id="436c2-151">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="436c2-151">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="436c2-152">Criando novas definições de configuração de reunião usando os cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="436c2-152">Creating New Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="436c2-153">As definições de configuração de reunião podem ser criadas (somente no escopo do site) usando o Windows PowerShell e o cmdlet New-CsMeetingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="436c2-153">Meeting configuration settings can be created (at the site scope only) by using Windows PowerShell and the New-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="436c2-154">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="436c2-154">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="436c2-155">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="436c2-155">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="436c2-156">Para criar definições de configuração de reunião que usam os valores padrão</span><span class="sxs-lookup"><span data-stu-id="436c2-156">To create meeting configuration settings that use the default values</span></span>

  - <span data-ttu-id="436c2-157">Este comando cria um novo conjunto de configurações de reunião para o site Redmond:</span><span class="sxs-lookup"><span data-stu-id="436c2-157">This command creates a new set of meeting configuration settings for the Redmond site:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="436c2-158">Como não há parâmetros (além do parâmetro obrigatório Identity) onde especificado no comando anterior, as novas definições de configuração de reunião usarão os valores padrões para todas as suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="436c2-158">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a><span data-ttu-id="436c2-159">Para alterar um valor de propriedade ao criar definições de configuração de reunião</span><span class="sxs-lookup"><span data-stu-id="436c2-159">To change a property value when creating meeting configuration settings</span></span>

  - <span data-ttu-id="436c2-p112">Para criar configurações que usam valores de propriedades diferentes, basta incluir o parâmetro e o valor de parâmetro adequados. Por exemplo, para criar um conjunto de reuniões de configuração da reunião que, por padrão, permite todos em uma reunião serem apresentadores a usarem um comando como este:</span><span class="sxs-lookup"><span data-stu-id="436c2-p112">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a><span data-ttu-id="436c2-162">Para alterar vários valores de propriedade ao criar definições de configuração de reunião</span><span class="sxs-lookup"><span data-stu-id="436c2-162">To change multiple property values when creating meeting configuration settings</span></span>

  - <span data-ttu-id="436c2-p113">Os valores de várias propriedades podem ser modificados, incluindo vários parâmetros. Por exemplo, este comando permite que todos em uma reunião serem apresentadores e também força os usuários PSTN a aguardar enquanto são formalmente admitidos na reunião:</span><span class="sxs-lookup"><span data-stu-id="436c2-p113">Multiple property values can be modified by including multiple parameters. For example, this command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

<span data-ttu-id="436c2-165">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="436c2-165">For more information, see the help topic for the [New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

