---
title: Personalizar a música de espera do Estacionamento de Chamada noSkype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Personalize a música de espera do Estacionamento de Chamada no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 766b51895acda27c0558352968d21a39764b13a6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837071"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="bdae5-103">Personalizar a música de espera do Estacionamento de Chamada noSkype for Business</span><span class="sxs-lookup"><span data-stu-id="bdae5-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="bdae5-104">Personalize a música de espera do Estacionamento de Chamada no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="bdae5-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="bdae5-105">Você pode especificar seu próprio arquivo de música a ser usado para música em espera, em vez do arquivo de música padrão que acompanha o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bdae5-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="bdae5-106">Para personalizar música em espera, utilize o cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.</span><span class="sxs-lookup"><span data-stu-id="bdae5-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bdae5-107">Se você personalizar música em espera e quiser a mesma música para vários sites, configure o arquivo de música para cada site que executa o aplicativo Estacionamento de Chamada.</span><span class="sxs-lookup"><span data-stu-id="bdae5-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="bdae5-108">Para personalizar o arquivo de música</span><span class="sxs-lookup"><span data-stu-id="bdae5-108">To customize the music file</span></span>

1. <span data-ttu-id="bdae5-109">Faça logoff no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário **necessários,** conforme descrito em Delegate Setup Permissions .</span><span class="sxs-lookup"><span data-stu-id="bdae5-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="bdae5-110">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="bdae5-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="bdae5-111">Execute:</span><span class="sxs-lookup"><span data-stu-id="bdae5-111">Run:</span></span>
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="bdae5-112">Utilize o cmdlet **Get-CsService** para identificar o serviço.</span><span class="sxs-lookup"><span data-stu-id="bdae5-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="bdae5-113">Para obter detalhes, [consulte Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="bdae5-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="bdae5-114">O exemplo a seguir mostra como obter o conteúdo de um arquivo, soothingmusic.wma, como uma matriz de byte e atribuí-lo a uma variável.</span><span class="sxs-lookup"><span data-stu-id="bdae5-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="bdae5-115">Então, o arquivo de áudio é atribuído como o arquivo de música em espera para Estacionamento de Chamada.</span><span class="sxs-lookup"><span data-stu-id="bdae5-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="bdae5-116">Para obter detalhes, [consulte Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="bdae5-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="bdae5-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="bdae5-117">See also</span></span>

[<span data-ttu-id="bdae5-118">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="bdae5-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="bdae5-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="bdae5-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
