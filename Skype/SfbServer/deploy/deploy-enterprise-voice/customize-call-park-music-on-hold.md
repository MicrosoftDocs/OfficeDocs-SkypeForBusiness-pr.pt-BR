---
title: Personalizar a música de estacionamento de chamada em espera inSkype for Business
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Personalize a música de espera no Skype para Business Server Enterprise Voice de estacionamento de chamadas.
ms.openlocfilehash: e3d1ccdf70278173bf5a3a448e5330a24879d117
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223181"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="a43c1-103">Personalizar a música de estacionamento de chamada em espera inSkype for Business</span><span class="sxs-lookup"><span data-stu-id="a43c1-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="a43c1-104">Personalize a música de espera no Skype para Business Server Enterprise Voice de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="a43c1-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="a43c1-105">Você pode especificar seu próprio arquivo de música a ser usado para a música em espera, em vez do arquivo de música padrão que acompanha o Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="a43c1-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="a43c1-106">Para personalizar música em espera, utilize o cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.</span><span class="sxs-lookup"><span data-stu-id="a43c1-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a43c1-107">Se você personalizar a música em espera e deseja a mesma música para vários sites, você deve configurar o arquivo de música para cada site que executa o aplicativo de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="a43c1-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="a43c1-108">Para personalizar o arquivo de música</span><span class="sxs-lookup"><span data-stu-id="a43c1-108">To customize the music file</span></span>

1. <span data-ttu-id="a43c1-109">Faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="a43c1-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="a43c1-110">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="a43c1-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a43c1-111">Execute:</span><span class="sxs-lookup"><span data-stu-id="a43c1-111">Run:</span></span>
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="a43c1-112">Utilize o cmdlet **Get-CsService** para identificar o serviço.</span><span class="sxs-lookup"><span data-stu-id="a43c1-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="a43c1-113">Para obter detalhes, consulte [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="a43c1-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="a43c1-114">O exemplo a seguir mostra como obter o conteúdo de um arquivo, soothingmusic.wma, como uma matriz de byte e atribuí-lo a uma variável.</span><span class="sxs-lookup"><span data-stu-id="a43c1-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="a43c1-115">Então, o arquivo de áudio é atribuído como o arquivo de música em espera para Estacionamento de Chamada.</span><span class="sxs-lookup"><span data-stu-id="a43c1-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="a43c1-116">Para obter detalhes, consulte [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="a43c1-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="a43c1-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="a43c1-117">See also</span></span>

[<span data-ttu-id="a43c1-118">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="a43c1-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="a43c1-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="a43c1-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
