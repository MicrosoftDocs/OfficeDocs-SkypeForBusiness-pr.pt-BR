---
title: Criar ou modificar um conjunto de definições de configuração de reunião
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
ms.openlocfilehash: 0a5f80066a68b45e062a351478bea93a5c2e8fd0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="3cacb-102">Criar ou modificar uma coleção de definições de configuração de reunião no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3cacb-102">Create or modify a collection of meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cacb-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3cacb-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3cacb-104">Você pode usar as configurações na página configuração de reunião para definir várias características da experiência de participação na reunião.</span><span class="sxs-lookup"><span data-stu-id="3cacb-104">You can use the settings on the Meeting Configuration page to define various characteristics of the meeting join experience.</span></span> <span data-ttu-id="3cacb-105">Por padrão, as configurações globais definem a experiência de junção.</span><span class="sxs-lookup"><span data-stu-id="3cacb-105">By default, the global settings define the join experience.</span></span> <span data-ttu-id="3cacb-106">Você também pode criar configurações em nível de site e de junção de reunião no nível do grupo.</span><span class="sxs-lookup"><span data-stu-id="3cacb-106">You can also create site-level and pool-level meeting join settings.</span></span> <span data-ttu-id="3cacb-107">Se você criar configurações no nível de pool, elas serão aplicadas a todas as reuniões hospedadas pelo pool.</span><span class="sxs-lookup"><span data-stu-id="3cacb-107">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="3cacb-108">Se você não criar configurações no nível de pool, as configurações do nível local serão aplicadas, caso existam.</span><span class="sxs-lookup"><span data-stu-id="3cacb-108">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="3cacb-109">Se você não definir as configurações de nível local, as configurações globais serão aplicadas a todas as reuniões.</span><span class="sxs-lookup"><span data-stu-id="3cacb-109">If you do not define site-level settings, the global settings apply to all meetings.</span></span>

<div>

## <a name="to-create-new-meeting-join-settings"></a><span data-ttu-id="3cacb-110">Para criar novas configurações de junção de reunião</span><span class="sxs-lookup"><span data-stu-id="3cacb-110">To create new meeting join settings</span></span>

1.  <span data-ttu-id="3cacb-111">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="3cacb-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3cacb-112">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3cacb-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3cacb-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3cacb-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3cacb-114">Na barra de navegação à esquerda, clique em **conferência** e em **configuração de reunião**.</span><span class="sxs-lookup"><span data-stu-id="3cacb-114">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="3cacb-115">Na página **Configuração de reunião**, clique em **Novo** e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="3cacb-115">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="3cacb-p103">Para criar uma política a nível local, clique em **Configuração local**. No campo de pesquisa **Selecionar um local**, digite todo ou parte do nome do local para o qual você deseja definir as configurações de participação de reunião. Na lista resultante de locais, clique no local desejado e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3cacb-p103">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="3cacb-p104">Para criar uma política a nível de pool, clique em **Configuração do pool**. No campo de pesquisa **Selecionar um serviço**, digite todo ou parte do nome do serviço do pool para o qual você deseja definir as configurações de participação de reunião. Na lista resultante de serviços, clique no pool desejado e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3cacb-p104">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="3cacb-p105">Para direcionar os participantes que ligam de um PSTN através do lobby, desmarque a caixa de seleção  **Chamadores PSTN ignoram o lobby**. Por padrão, os participantes discando pelo PSTN irão diretamente para a reunião.</span><span class="sxs-lookup"><span data-stu-id="3cacb-p105">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>

6.  <span data-ttu-id="3cacb-124">Para configurar quem pode ser um apresentador na reunião, em **Designar como apresentador**, siga um dos procedimentos abaixo:</span><span class="sxs-lookup"><span data-stu-id="3cacb-124">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
      - <span data-ttu-id="3cacb-125">Para não permitir que qualquer pessoa além do organizador seja o apresentador, clique em **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="3cacb-125">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
      - <span data-ttu-id="3cacb-p106">Para permitir que apenas participantes membros da sua organização sejam apresentadores, clique em **Empresa**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="3cacb-p106">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
      - <span data-ttu-id="3cacb-128">Para permitir que qualquer participante seja o apresentador, clique em **Todos**.</span><span class="sxs-lookup"><span data-stu-id="3cacb-128">To allow any participants to be a presenter, click **Everyone**.</span></span>

7.  <span data-ttu-id="3cacb-p107">Para que o organizador selecione um tipo de conferência ao programar uma reunião, desmarque a caixa de seleção  **Tipo de conferência atribuída por padrão**. Por padrão, o tipo de conferência é atribuído automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3cacb-p107">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>

8.  <span data-ttu-id="3cacb-p108">Para evitar que usuários anônimos (não autenticados) sejam aceitos automaticamente, desmarque a caixa de seleção **Aceitar usuários anônimos por padrão**. Por padrão, os usuários anônimos são aceitos automaticamente nas reuniões.</span><span class="sxs-lookup"><span data-stu-id="3cacb-p108">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>

9.  <span data-ttu-id="3cacb-133">Para personalizar o convite da reunião enviado para os participantes, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="3cacb-133">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="3cacb-134">Observe que o comprimento máximo das URLs e o texto do rodapé padrão é de 1KB.</span><span class="sxs-lookup"><span data-stu-id="3cacb-134">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="3cacb-135">Exceto para a **URL de ajuda**, se você não especificar um valor para as personalizações, elas não serão incluídas na reunião.</span><span class="sxs-lookup"><span data-stu-id="3cacb-135">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="3cacb-136">Se você não incluir uma URL de ajuda personalizada, a URL da ajuda padrão do Lync será exibida no convite.</span><span class="sxs-lookup"><span data-stu-id="3cacb-136">If you do not include a custom help URL, the default help URL for Lync will be displayed in the invite.</span></span>
    
      - <span data-ttu-id="3cacb-137">Para personalizar o logotipo exibido no convite da reunião, na **URL do Logotipo**, insira o local do logotipo.</span><span class="sxs-lookup"><span data-stu-id="3cacb-137">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="3cacb-138">O logotipo deve ser uma imagem GIF ou JPG com um tamanho de 188 por 30 pixels.</span><span class="sxs-lookup"><span data-stu-id="3cacb-138">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span>

        
        </div>
    
      - <span data-ttu-id="3cacb-139">Para personalizar o texto de ajuda exibido no convite da reunião, na **URL de ajuda**, insira o local do texto de ajuda.</span><span class="sxs-lookup"><span data-stu-id="3cacb-139">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
      - <span data-ttu-id="3cacb-140">Para personalizar o texto legal exibido no convite da reunião, na **URL do texto legal**, insira o texto legal.</span><span class="sxs-lookup"><span data-stu-id="3cacb-140">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
      - <span data-ttu-id="3cacb-141">Para personalizar o texto do rodapé exibido no convite da reunião, em **Texto do rodapé personalizado**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="3cacb-141">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>

10. <span data-ttu-id="3cacb-142">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="3cacb-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a><span data-ttu-id="3cacb-143">Para modificar uma coleção existente de configurações de reunião</span><span class="sxs-lookup"><span data-stu-id="3cacb-143">To modify an existing collection of meeting configurations</span></span>

1.  <span data-ttu-id="3cacb-144">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="3cacb-144">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3cacb-145">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3cacb-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3cacb-146">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3cacb-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3cacb-147">Na barra de navegação à esquerda, clique em **conferência** e em **configuração de reunião**.</span><span class="sxs-lookup"><span data-stu-id="3cacb-147">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="3cacb-148">Na lista de configurações da reunião, clique na configuração que deseja alterar, em **Editar** e, em seguida, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="3cacb-148">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3cacb-149">Em **Editar configuração da reunião**, modifique qualquer definição da configuração, exceto o nome da configuração, que não pode ser modificado.</span><span class="sxs-lookup"><span data-stu-id="3cacb-149">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>

6.  <span data-ttu-id="3cacb-150">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="3cacb-150">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3cacb-151">Criando novas definições de configuração de reunião usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3cacb-151">Creating New Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3cacb-152">As configurações de reunião podem ser criadas (somente no escopo do site) usando o Windows PowerShell e o cmdlet New-CsMeetingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="3cacb-152">Meeting configuration settings can be created (at the site scope only) by using Windows PowerShell and the New-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="3cacb-153">Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3cacb-153">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3cacb-154">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="3cacb-154">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="3cacb-155">Para criar definições de configuração de reunião que usam os valores padrão</span><span class="sxs-lookup"><span data-stu-id="3cacb-155">To create meeting configuration settings that use the default values</span></span>

  - <span data-ttu-id="3cacb-156">Esse comando cria um novo conjunto de definições de configuração de reunião para o site Redmond:</span><span class="sxs-lookup"><span data-stu-id="3cacb-156">This command creates a new set of meeting configuration settings for the Redmond site:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="3cacb-157">Como não há parâmetros (além do parâmetro obrigatório Identity) onde especificado no comando anterior, as novas definições de configuração de reunião usarão os valores padrões para todas as suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="3cacb-157">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a><span data-ttu-id="3cacb-158">Para alterar um valor de propriedade ao criar definições de configuração de reunião</span><span class="sxs-lookup"><span data-stu-id="3cacb-158">To change a property value when creating meeting configuration settings</span></span>

  - <span data-ttu-id="3cacb-p112">Para criar configurações que usam valores de propriedades diferentes, basta incluir o parâmetro e o valor de parâmetro adequados. Por exemplo, para criar um conjunto de reuniões de configuração da reunião que, por padrão, permite todos em uma reunião serem apresentadores a usarem um comando como este:</span><span class="sxs-lookup"><span data-stu-id="3cacb-p112">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a><span data-ttu-id="3cacb-161">Para alterar vários valores de propriedade ao criar definições de configuração de reunião</span><span class="sxs-lookup"><span data-stu-id="3cacb-161">To change multiple property values when creating meeting configuration settings</span></span>

  - <span data-ttu-id="3cacb-162">Vários valores de propriedade podem ser modificados incluindo vários parâmetros.</span><span class="sxs-lookup"><span data-stu-id="3cacb-162">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="3cacb-163">Por exemplo, esse comando admite todas as pessoas em uma reunião como apresentador e também obriga os usuários de PSTN a aguardar no lobby até que sejam formadas de forma reconhecidas para a reunião:</span><span class="sxs-lookup"><span data-stu-id="3cacb-163">For example, this command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

<span data-ttu-id="3cacb-164">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="3cacb-164">For more information, see the help topic for the [New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

