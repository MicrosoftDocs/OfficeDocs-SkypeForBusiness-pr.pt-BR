---
title: 'Lync Server 2013: exibir informações da política de conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View conferencing policy information
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49733852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8dc9174356b1d5f8e5c6316ef761c51db1eb969
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-conferencing-policy-information-in-lync-server-2013"></a><span data-ttu-id="d9ad8-102">Exibir informações de política de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9ad8-102">View conferencing policy information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9ad8-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d9ad8-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d9ad8-104">No painel de controle do Lync Server 2013, você usa políticas de conferência para controlar como a conferência é implementada na sua implantação.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-104">In Lync Server 2013 Control Panel, you use conferencing policies to control how conferencing is implemented in your deployment.</span></span> <span data-ttu-id="d9ad8-105">Isso inclui as seguintes políticas de conferência:</span><span class="sxs-lookup"><span data-stu-id="d9ad8-105">This includes the following conferencing policies:</span></span>

  - <span data-ttu-id="d9ad8-106">Uma política global criada por padrão quando você implanta o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="d9ad8-107">Política opcional no nível do site e no nível do usuário que você pode criar e usar para especificar como a conferência é implementada para sites ou usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-107">Optional site-level and user-level policy that you can create and use to specify how conferencing is implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-conferencing-policy-settings"></a><span data-ttu-id="d9ad8-108">Para exibir as configurações da política de conferência</span><span class="sxs-lookup"><span data-stu-id="d9ad8-108">To view conferencing policy settings</span></span>

1.  <span data-ttu-id="d9ad8-109">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d9ad8-110">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d9ad8-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d9ad8-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d9ad8-112">Na barra de navegação à esquerda, clique em **conferência** e, em seguida, clique em **política de conferência**.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-112">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="d9ad8-113">Na página de **Política de Conferência**, dê um clique duplo na política de conferência que você deseja visualizar.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-113">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>

5.  <span data-ttu-id="d9ad8-114">Em **Editar Filtro de arquivo**, selecione **Mostrar detalhes...**</span><span class="sxs-lookup"><span data-stu-id="d9ad8-114">In **Edit File Filter**, select the **Show Details…**</span></span> <span data-ttu-id="d9ad8-115">caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-115">check box.</span></span>
    
    <span data-ttu-id="d9ad8-116">**Editar política de conferência \<–\> a política** é aberta exibindo as configurações da política selecionada.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-116">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="d9ad8-117">Para obter detalhes sobre como definir as configurações, consulte [criar ou modificar uma política de conferência no Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="d9ad8-117">For details about configuring the settings, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

</div>

<div>

## <a name="viewing-conferencing-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d9ad8-118">Exibindo políticas de conferência usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d9ad8-118">Viewing Conferencing Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d9ad8-119">As políticas de conferência podem ser exibidas usando o Windows PowerShell e o cmdlet Get-CsConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-119">Conferencing policies can be viewed by using Windows PowerShell and the Get-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="d9ad8-120">Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d9ad8-121">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="d9ad8-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-conferencing-policies"></a><span data-ttu-id="d9ad8-122">Para exibir as políticas de conferência</span><span class="sxs-lookup"><span data-stu-id="d9ad8-122">To view conferencing policies</span></span>

  - <span data-ttu-id="d9ad8-123">Para ver as informações sobre todas as suas políticas de conferência, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="d9ad8-123">To view information about all your conferencing policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="d9ad8-124">Isso retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="d9ad8-124">That will return information similar to this:</span></span>
    
        Identity                                  : Global
        AllowIPAudio                              : True
        AllowIPVideo                              : True
        AllowMultiView                            : True
        Description                               :
        AllowParticipantControl                   : True
        AllowAnnotations                          : True
        DisablePowerPointAnnotations              : False
        AllowUserToScheduleMeetingsWithAppSharing : True
        AllowNonEnterpriseVoiceUsersToDialOut     : False
        AllowAnonymousUsersToDialOut              : False
        AllowAnonymousParticipantsInMeetings      : True
        AllowExternalUsersToSaveContent           : True
        AllowExternalUserControl                  : False
        AllowExternalUsersToRecordMeeting         : False
        AllowPolls                                : True
        AllowSharedNotes                          : True
        EnableDialInConferencing                  : True
        EnableAppDesktopSharing                   : Desktop
        AllowConferenceRecording                  : False
        EnableP2PRecording                        : False
        EnableFileTransfer                        : True
        EnableP2PFileTransfer                     : True
        EnableP2PVideo                            : True
        AllowLargeMeetings                        : False
        EnableDataCollaboration                   : True
        MaxVideoConferenceResolution              : VGA
        MaxMeetingSize                            : 250
        AudioBitRateKb                            : 200
        VideoBitRateKb                            : 50000
        AppSharingBitRateKb                       : 50000
        FileTransferBitRateKb                     : 50000
        TotalReceiveVideoBitRateKb                : 6000
        EnableMultiViewJoin                       : True

</div>

<span data-ttu-id="d9ad8-125">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) .</span><span class="sxs-lookup"><span data-stu-id="d9ad8-125">For more information, see the help topic for the [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

