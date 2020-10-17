---
title: 'Lync Server 2013: personalizar o estacionamento de chamada música em espera'
description: 'Lync Server 2013: Personalizar música de estacionamento de chamada em espera.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customize Call Park music on hold
ms:assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688031(v=OCS.15)
ms:contentKeyID: 49733621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19219e4a77d4be4a18a43255e142339a4af6f463
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543997"
---
# <a name="customize-call-park-music-on-hold-in-lync-server-2013"></a><span data-ttu-id="f99f9-103">Personalizar o estacionamento de chamada música em espera no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f99f9-103">Customize Call Park music on hold in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f99f9-104">_**Última modificação do tópico:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="f99f9-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="f99f9-105">Você pode especificar seu próprio arquivo de música para usar para música em espera, em vez do arquivo de música padrão que acompanha o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f99f9-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Lync Server 2013.</span></span> <span data-ttu-id="f99f9-106">Para personalizar música em espera, utilize o cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.</span><span class="sxs-lookup"><span data-stu-id="f99f9-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f99f9-107">Se você personalizar a música em espera e quiser a mesma música para vários sites, deverá configurar o arquivo de música para cada site que executa o aplicativo de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="f99f9-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span>



</div>

<div>

## <a name="to-customize-the-music-file"></a><span data-ttu-id="f99f9-108">Para personalizar o arquivo de música</span><span class="sxs-lookup"><span data-stu-id="f99f9-108">To customize the music file</span></span>

1.  <span data-ttu-id="f99f9-109">Faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f99f9-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f99f9-110">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f99f9-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f99f9-111">Sejam</span><span class="sxs-lookup"><span data-stu-id="f99f9-111">Run:</span></span>
    
        Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte[]>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="f99f9-112">Utilize o cmdlet <STRONG>Get-CsService</STRONG> para identificar o serviço.</span><span class="sxs-lookup"><span data-stu-id="f99f9-112">Use the <STRONG>Get-CsService</STRONG> cmdlet to identify the service.</span></span> <span data-ttu-id="f99f9-113">Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get-CsService</A>.</span><span class="sxs-lookup"><span data-stu-id="f99f9-113">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get-CsService</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="f99f9-114">O exemplo a seguir mostra como obter o conteúdo de um arquivo, soothingmusic.wma, como uma matriz de byte e atribuí-lo a uma variável.</span><span class="sxs-lookup"><span data-stu-id="f99f9-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="f99f9-115">Então, o arquivo de áudio é atribuído como o arquivo de música em espera para Estacionamento de Chamada.</span><span class="sxs-lookup"><span data-stu-id="f99f9-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="f99f9-116">Para obter detalhes, consulte [set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).</span><span class="sxs-lookup"><span data-stu-id="f99f9-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).</span></span>
    
        $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
        Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f99f9-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="f99f9-117">See Also</span></span>


[<span data-ttu-id="f99f9-118">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="f99f9-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)  
[<span data-ttu-id="f99f9-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="f99f9-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

