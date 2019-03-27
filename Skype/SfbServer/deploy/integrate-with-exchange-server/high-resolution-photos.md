---
title: Configurar o uso de fotos de alta resolução no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 'Resumo: Configure o uso de fotos de alta resolução no Exchange Server 2016 ou Exchange Server 2013 e Skype para Business Server.'
ms.openlocfilehash: 56fef2cfa8c62a66698c2232c9273cdb5604b5b8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875430"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>Configurar o uso de fotos de alta resolução no Skype para Business Server
 
**Resumo:** Configure o uso de fotos de alta resolução no Exchange Server 2016 ou Exchange Server 2013 e Skype para Business Server.
  
No Skype para Business Server fotos podem ser armazenadas em um Exchange Server 2016 ou Exchange Server 2013 de correio do usuário, que permite os tamanhos de foto até 648 pixels por 648 pixels. Além disso, Exchange Server pode redimensionar automaticamente essas fotos para uso nos produtos diferentes conforme necessário. Geralmente, isso significa três tamanhos e resoluções de fotos diferentes.
  
- 64 pixels por 64 pixels, o tamanho utilizado pelo atributo thumbnailPhoto do Active Directory. Se você carregar uma foto para Exchange Server, Exchange criará automaticamente um pixel 64 pela versão de 64 pixel dessa foto e atualizar o atributo thumbnailPhoto do usuário. No entanto, observe que o inverso não é verdadeiro: se você atualizar manualmente o atributo thumbnailPhoto do Active Directory a foto de correio do Exchange do usuário não serão automaticamente atualizada.
    
- 96 pixels por 96 pixels, para uso no Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype para negócios Web App e Skype para negócios.
    
- 648 pixels por 648 pixels para usam no Skype para comerciais e Skype para negócios Web App Skype para negócios Web App.
    
> [!NOTE]
> Se você tiver os recursos, é recomendável que você carrega fotos 648 x 648; que fornece a resolução máxima e a qualidade de imagem ideal em qualquer um dos aplicativos do Office 2013. Cada foto JPEG com um tamanho de 648 x 648 e uma profundidade de 24 bits resulta em um tamanho de arquivo de aproximadamente 240 quilobytes. Isso significa que você precisará de aproximadamente 1 megabyte de espaço em disco para cada 4 fotos de usuário. 
  
Fotos de alta resolução, que são acessadas usando serviços Web do Exchange, podem ser carregadas por usuários que estão executando o Outlook 2013 Web App; os usuários somente poderão atualizar sua própria foto. Os administradores, no entanto, podem atualizar a foto para qualquer usuário usando o Shell de gerenciamento do Exchange e uma série de comandos do Windows PowerShell semelhantes ao seguinte:
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

O primeiro comando no exemplo anterior usa o `Get-Content` cmdlet para ler o conteúdo do arquivo C:\Photos\Kenmyer.jpg e armazenar os dados em uma variável denominada $photo. No segundo comando, o cmdlet do Exchange `Set-UserPhoto` é usado para carregar a foto e anexe esse foto à conta de usuário de Ken Myer.
  
> [!NOTE]
> Neste exemplo, o nome de exibição do Active Directory de Ken Myer é usado como a identidade da conta de usuário. Você também pode referenciar uma conta de usuário usando outros identificadores como endereço SMTP do usuário ou seu nome principal de usuário. Consulte a documentação para o cmdlet Set-UserPhoto em [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) para obter mais informações
  
Carregar a foto não é o mesmo que atribuir essa foto à conta de usuário de Ken Myer. Em vez disso, carregar a foto simplesmente resulta em uma visualização da foto a ser exibida na página Opções do Outlook Web App. Para realmente atribuir essa foto à conta de usuário, o usuário deve clicar em **Salvar**, na página Opções, ou o administrador deve executar o terceiro comando do exemplo. Esse terceiro comando usa o parâmetro Salvar para atribuir a foto à conta de usuário de Ken Myer.
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Para verificar que a nova foto foi atribuída à conta de usuário, Ken Myer pode fazer logon no Skype para negócios, selecione as **Opções**e selecione **Minha imagem**. A foto recém-carregada deve ser exibida como a foto pessoal de Ken. Como alternativa, os administradores podem verificar a foto de qualquer usuário iniciando o Internet Explorer e navegando até uma URL parecida com esta:
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

Se o administrador pode exibir a foto usando o Internet Explorer, mas o usuário não pode exibir sua foto no Skype para negócios pode haver um problema de conectividade com serviços Web do Exchange ou com o serviço de descoberta automática do Exchange.
  
Observe também que nenhuma configuração adicional é necessário para disponibilizar esta foto em Skype para negócios. Em vez disso, a foto estarão disponível instantaneamente após ele ter sido carregado e o `Set-UserPhoto` cmdlet tenha sido executado.
