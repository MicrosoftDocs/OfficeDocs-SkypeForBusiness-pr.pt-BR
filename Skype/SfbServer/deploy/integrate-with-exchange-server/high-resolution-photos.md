---
title: Configurar o uso de fotos de alta resolução no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 'Resumo: configurar o uso de fotos de alta resolução no Exchange Server 2016 ou no Exchange Server 2013 e no Skype for Business Server.'
ms.openlocfilehash: 1ca9c0077969cab22b8ebfa073d3d0585108503b
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464650"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>Configurar o uso de fotos de alta resolução no Skype for Business Server
 
**Resumo:** Configurar o uso de fotos de alta resolução no Exchange Server 2016 ou no Exchange Server 2013 e no Skype for Business Server.
  
As fotos do Skype for Business Server podem ser armazenadas em uma caixa de correio do Exchange Server 2016 ou do Exchange Server 2013 do usuário, o que permite tamanhos de fotos de até 648 pixels por 648 pixels. Além disso, o Exchange Server pode redimensionar automaticamente essas fotos para uso em diferentes produtos, conforme necessário. Geralmente, isso significa três tamanhos e resoluções de fotos diferentes.
  
- 64 pixels por 64 pixels, o tamanho utilizado pelo atributo thumbnailPhoto do Active Directory. Se você carregar uma foto no Exchange Server, o Exchange criará automaticamente uma versão de 64 pixel por 64 pixels dessa foto e atualizará o atributo thumbnailPhoto do usuário. Observe, porém, que o inverso não é verdadeiro: se você atualizar manualmente o atributo thumbnailPhoto no Active Directory, a foto na caixa de correio do Exchange do usuário não será atualizada automaticamente.
    
- 96 pixels por 96 pixels, para uso no Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App e Skype for Business.
    
- 648 pixels por 648 pixels para uso no Skype for Business e no Skype for Business Web App Web App.
    
> [!NOTE]
> Se você tiver os recursos, é recomendável carregar 648 x 648 fotos; Isso fornece a resolução máxima e a qualidade de imagem ideal em qualquer um dos aplicativos do Office 2013. Cada foto JPEG com um tamanho de 648 x 648 e uma profundidade de 24 bits resulta em um tamanho de arquivo de aproximadamente 240 kilobytes. Isso significa que você precisará de aproximadamente 1 megabyte de espaço em disco para cada 4 fotos de usuário. 
  
Fotos de alta resolução, que são acessadas usando serviços Web do Exchange, podem ser carregadas pelos usuários que executam o Outlook 2013 Web App; os usuários só têm permissão para atualizar sua própria foto. No entanto, os administradores podem atualizar a foto para qualquer usuário usando o Shell de gerenciamento do Exchange e vários comandos do Windows PowerShell semelhantes ao seguinte:
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

O primeiro comando no exemplo anterior usa o `Get-Content` cmdlet para ler o conteúdo do arquivo C:\Photos\Kenmyer.jpg e armazenar esses dados em uma variável chamada $Photo. No segundo comando, o cmdlet `Set-UserPhoto` do Exchange é usado para carregar a foto e anexar essa foto à conta de usuário de Ken Myer.
  
> [!NOTE]
> Neste exemplo, o nome de exibição do Active Directory de Ken Myer é usado como a identidade da conta de usuário. Você também pode referenciar uma conta de usuário usando outros identificadores como endereço SMTP do usuário ou seu nome principal de usuário. Consulte a documentação do cmdlet Set-UserPhoto em [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) para obter mais informações
  
Carregar a foto não é o mesmo que atribuir essa foto à conta de usuário de Ken Myer. Em vez disso, carregar a foto simplesmente resulta em uma visualização da foto a ser exibida na página Opções do Outlook Web App. Para realmente atribuir essa foto à conta de usuário, o usuário deve clicar em **Salvar**, na página Opções, ou o administrador deve executar o terceiro comando do exemplo. Esse terceiro comando usa o parâmetro Salvar para atribuir a foto à conta de usuário de Ken Myer.
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Para verificar se a nova foto foi atribuída à conta de usuário, Ken Myer pode fazer logon no Skype for Business, selecionar **Opções**e, em seguida, selecionar **minha imagem**. A foto recém-carregada deve ser exibida como a foto pessoal de Ken. Como alternativa, os administradores podem verificar a foto de qualquer usuário iniciando o Internet Explorer e navegando até uma URL parecida com esta:
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

Se o administrador puder ver a foto usando o Internet Explorer, mas o usuário não puder ver sua foto no Skype for Business, talvez haja um problema de conectividade com os serviços Web do Exchange ou com o serviço de descoberta automática do Exchange.
  
Observe também que nenhuma configuração adicional é necessária para disponibilizar essa foto no Skype for Business. Em vez disso, a foto estará disponível instantaneamente após o carregamento e o `Set-UserPhoto` cmdlet tiver sido executado.
