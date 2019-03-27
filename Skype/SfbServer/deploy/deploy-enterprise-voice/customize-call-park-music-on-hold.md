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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895430"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>Personalizar a música de estacionamento de chamada em espera inSkype for Business
 
Personalize a música de espera no Skype para Business Server Enterprise Voice de estacionamento de chamadas.
  
Você pode especificar seu próprio arquivo de música a ser usado para a música em espera, em vez do arquivo de música padrão que acompanha o Skype para Business Server. Para personalizar música em espera, utilize o cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.
  
> [!NOTE]
> Se você personalizar a música em espera e deseja a mesma música para vários sites, você deve configurar o arquivo de música para cada site que executa o aplicativo de estacionamento de chamadas. 
  
### <a name="to-customize-the-music-file"></a>Para personalizar o arquivo de música

1. Faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **Delegate Setup Permissions**.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Execute:
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > Utilize o cmdlet **Get-CsService** para identificar o serviço. Para obter detalhes, consulte [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps). 
  
    O exemplo a seguir mostra como obter o conteúdo de um arquivo, soothingmusic.wma, como uma matriz de byte e atribuí-lo a uma variável. Então, o arquivo de áudio é atribuído como o arquivo de música em espera para Estacionamento de Chamada. Para obter detalhes, consulte [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>Consulte Também

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
