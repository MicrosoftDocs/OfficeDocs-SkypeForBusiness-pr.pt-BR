---
title: 'Lync Server 2013: personalizar a chamada de música do parque em espera'
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
ms.openlocfilehash: 301625a36d23c69d02dfdcde8c4985def53630af
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="customize-call-park-music-on-hold-in-lync-server-2013"></a><span data-ttu-id="435ef-102">Personalizar a chamada de música do parque em espera no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="435ef-102">Customize Call Park music on hold in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="435ef-103">_**Tópico da última modificação:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="435ef-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="435ef-104">Você pode especificar seu próprio arquivo de música para usar para música em espera, em vez do arquivo de música padrão que acompanha o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="435ef-104">You can specify your own music file to use for music on hold, instead of the default music file that ships with Lync Server 2013.</span></span> <span data-ttu-id="435ef-105">Para personalizar música em espera, utilize o cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.</span><span class="sxs-lookup"><span data-stu-id="435ef-105">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="435ef-106">Se você personalizar música em espera e quiser a mesma música para vários sites, deve configurar o arquivo de música para cada site que executa o aplicativo de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="435ef-106">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span>



</div>

<div>

## <a name="to-customize-the-music-file"></a><span data-ttu-id="435ef-107">Para personalizar o arquivo de música</span><span class="sxs-lookup"><span data-stu-id="435ef-107">To customize the music file</span></span>

1.  <span data-ttu-id="435ef-108">Faça logon no computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [permissões de configuração de representante no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="435ef-108">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="435ef-109">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="435ef-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="435ef-110">Execute:</span><span class="sxs-lookup"><span data-stu-id="435ef-110">Run:</span></span>
    
        Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte[]>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="435ef-111">Utilize o cmdlet <STRONG>Get-CsService</STRONG> para identificar o serviço.</span><span class="sxs-lookup"><span data-stu-id="435ef-111">Use the <STRONG>Get-CsService</STRONG> cmdlet to identify the service.</span></span> <span data-ttu-id="435ef-112">Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get-CsService</A>.</span><span class="sxs-lookup"><span data-stu-id="435ef-112">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get-CsService</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="435ef-113">O exemplo a seguir mostra como obter o conteúdo de um arquivo, soothingmusic.wma, como uma matriz de byte e atribuí-lo a uma variável.</span><span class="sxs-lookup"><span data-stu-id="435ef-113">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="435ef-114">Então, o arquivo de áudio é atribuído como o arquivo de música em espera para Estacionamento de Chamada.</span><span class="sxs-lookup"><span data-stu-id="435ef-114">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="435ef-115">Para obter detalhes, consulte [set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).</span><span class="sxs-lookup"><span data-stu-id="435ef-115">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).</span></span>
    
        $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
        Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="435ef-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="435ef-116">See Also</span></span>


[<span data-ttu-id="435ef-117">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="435ef-117">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)  
[<span data-ttu-id="435ef-118">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="435ef-118">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

