---
title: 'Lync Server 2013: exibir informações de política de conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing policy information
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49733852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59bbdf688066ef38e3327586b387f470c51d9c02
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-conferencing-policy-information-in-lync-server-2013"></a><span data-ttu-id="b96da-102">Exibir informações de política de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b96da-102">View conferencing policy information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b96da-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b96da-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b96da-104">No painel de controle do Lync Server 2013, você usa políticas de conferência para controlar como a conferência é implementada em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="b96da-104">In Lync Server 2013 Control Panel, you use conferencing policies to control how conferencing is implemented in your deployment.</span></span> <span data-ttu-id="b96da-105">Isso inclui as políticas de conferência a seguir:</span><span class="sxs-lookup"><span data-stu-id="b96da-105">This includes the following conferencing policies:</span></span>

  - <span data-ttu-id="b96da-106">Uma política global criada por padrão ao implantar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b96da-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="b96da-107">Políticas de nível de usuário e site opcionais que você pode criar e usar para especificar como conferências são implementadas para sites ou usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="b96da-107">Optional site-level and user-level policy that you can create and use to specify how conferencing is implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-conferencing-policy-settings"></a><span data-ttu-id="b96da-108">Para visualizar configurações de política de conferência</span><span class="sxs-lookup"><span data-stu-id="b96da-108">To view conferencing policy settings</span></span>

1.  <span data-ttu-id="b96da-109">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b96da-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b96da-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b96da-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b96da-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b96da-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b96da-112">Na barra de navegação esquerda, clique em **Conferência** e então clique em **Política de Conferência**.</span><span class="sxs-lookup"><span data-stu-id="b96da-112">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="b96da-113">Na página de **Política de Conferência**, dê um clique duplo na política de conferência que você deseja visualizar.</span><span class="sxs-lookup"><span data-stu-id="b96da-113">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>

5.  <span data-ttu-id="b96da-p103">Em **Editar Filtro de Arquivo**, marque a caixa de seleção **Mostrar Detalhes…**.</span><span class="sxs-lookup"><span data-stu-id="b96da-p103">In **Edit File Filter**, select the **Show Details…** check box.</span></span>
    
    <span data-ttu-id="b96da-116">**Editar política de conferência \<-\> a política** abre exibindo as configurações da política selecionada.</span><span class="sxs-lookup"><span data-stu-id="b96da-116">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="b96da-117">Para obter detalhes sobre como definir as configurações, consulte [create or Modify a Conferencing Policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="b96da-117">For details about configuring the settings, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

</div>

<div>

## <a name="viewing-conferencing-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b96da-118">Exibindo políticas de conferência usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b96da-118">Viewing Conferencing Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b96da-119">As políticas de conferência podem ser exibidas usando o Windows PowerShell e o cmdlet Get-CsConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="b96da-119">Conferencing policies can be viewed by using Windows PowerShell and the Get-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="b96da-120">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b96da-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b96da-121">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="b96da-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-conferencing-policies"></a><span data-ttu-id="b96da-122">Para exibir políticas de conferência</span><span class="sxs-lookup"><span data-stu-id="b96da-122">To view conferencing policies</span></span>

  - <span data-ttu-id="b96da-123">Para exibir informações sobre todas as suas políticas de conferência, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="b96da-123">To view information about all your conferencing policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="b96da-124">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="b96da-124">That will return information similar to this:</span></span>
    
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

<span data-ttu-id="b96da-125">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) .</span><span class="sxs-lookup"><span data-stu-id="b96da-125">For more information, see the help topic for the [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

