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
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>Personalizar a música de espera do Estacionamento de Chamada noSkype for Business
 
Personalize a música de espera do Estacionamento de Chamada no Skype for Business Server Enterprise Voice.
  
Você pode especificar seu próprio arquivo de música a ser usado para música em espera, em vez do arquivo de música padrão que acompanha o Skype for Business Server. Para personalizar música em espera, utilize o cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.
  
> [!NOTE]
> Se você personalizar música em espera e quiser a mesma música para vários sites, configure o arquivo de música para cada site que executa o aplicativo Estacionamento de Chamada. 
  
### <a name="to-customize-the-music-file"></a>Para personalizar o arquivo de música

1. Faça logoff no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário **necessários,** conforme descrito em Delegate Setup Permissions .
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**
    
3. Execute:
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > Utilize o cmdlet **Get-CsService** para identificar o serviço. Para obter detalhes, [consulte Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps). 
  
    O exemplo a seguir mostra como obter o conteúdo de um arquivo, soothingmusic.wma, como uma matriz de byte e atribuí-lo a uma variável. Então, o arquivo de áudio é atribuído como o arquivo de música em espera para Estacionamento de Chamada. Para obter detalhes, [consulte Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>Confira também

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
