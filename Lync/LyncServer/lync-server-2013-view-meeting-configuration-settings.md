---
title: 'Lync Server 2013: Exibir definições de configuração de reunião'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5daca87d47fdeb4bac46d83d48652037d75220b5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="c7bce-102">Exibir definições de configuração de reunião no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7bce-102">View meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7bce-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c7bce-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c7bce-104">No painel de controle do Lync Server 2013, você usa a configuração de reunião para controlar como as reuniões são implementadas em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="c7bce-104">In Lync Server 2013 Control Panel, you use meeting configuration setting to control how meetings are implemented in your deployment.</span></span> <span data-ttu-id="c7bce-105">Isto inclui a seguintes configurações de reunião:</span><span class="sxs-lookup"><span data-stu-id="c7bce-105">This includes the following meeting configurations:</span></span>

  - <span data-ttu-id="c7bce-106">Uma configuração global criada por padrão ao implantar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c7bce-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="c7bce-107">Configurações a nível do usuário ou do site opcionais que você cria e usa para especificar como as reuniões são implementadas para sites ou usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="c7bce-107">Optional site-level and user-level configurations that you can create and use to specify how meetings are implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-meeting-configuration-settings"></a><span data-ttu-id="c7bce-108">Para exibir configurações de reunião</span><span class="sxs-lookup"><span data-stu-id="c7bce-108">To view meeting configuration settings</span></span>

1.  <span data-ttu-id="c7bce-109">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="c7bce-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c7bce-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7bce-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c7bce-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c7bce-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c7bce-112">Na barra de navegação esquerda, clique em **Conferência** e em **Configuração da reunião**.</span><span class="sxs-lookup"><span data-stu-id="c7bce-112">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="c7bce-113">Na página **Configuração de Reunião**, clique na configuração de reunião que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="c7bce-113">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>

5.  <span data-ttu-id="c7bce-p103">Em **Editar Filtro de Arquivo**, marque a caixa de seleção **Mostrar detalhes...**.</span><span class="sxs-lookup"><span data-stu-id="c7bce-p103">In **Edit File Filter**, select the **Show Details…** check box.</span></span>
    
    <span data-ttu-id="c7bce-116">**Editar configuração de reunião \<-\> a política** abre exibindo as configurações da política selecionada.</span><span class="sxs-lookup"><span data-stu-id="c7bce-116">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="c7bce-117">Para obter detalhes sobre como definir as configurações, consulte [create or Modify a Collection of Meeting Configuration Settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="c7bce-117">For details about configuring the settings, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span>

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c7bce-118">Exibindo informações de configuração de reunião usando os cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c7bce-118">Viewing Meeting Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c7bce-119">As definições de configuração de reunião podem ser exibidas usando o Windows PowerShell e o cmdlet Get-CsMeetingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="c7bce-119">Meeting configuration settings can be viewed by using Windows PowerShell and the Get-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="c7bce-120">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7bce-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c7bce-121">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="c7bce-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-meeting-configuration-information"></a><span data-ttu-id="c7bce-122">Para exibir informações de configuração de reunião</span><span class="sxs-lookup"><span data-stu-id="c7bce-122">To view meeting configuration information</span></span>

  - <span data-ttu-id="c7bce-123">Para exibir informações sobre todas as suas definições de configuração de reunião, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="c7bce-123">To view information about all your meeting configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsMeetingConfiguration
    
    <span data-ttu-id="c7bce-124">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="c7bce-124">That will return information similar to this:</span></span>
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

</div>

<span data-ttu-id="c7bce-125">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="c7bce-125">For more information, see the help topic for the [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

