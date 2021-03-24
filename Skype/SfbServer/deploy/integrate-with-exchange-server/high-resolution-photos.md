---
title: Configurar o uso de fotos de alta resolução no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 'Resumo: Configure o uso de fotos de alta resolução no Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 ou Exchange Online e Skype for Business Server.'
ms.openlocfilehash: f5cc44f9f390c1d3241e7fae68054754ff7b0f76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109797"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>Configurar o uso de fotos de alta resolução no Skype for Business Server
 
**Resumo:** Configure o uso de fotos de alta resolução no Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 ou Exchange Online e Skype for Business Server.
  
No Skype for Business Server, as fotos podem ser armazenadas na caixa de correio do Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 ou exchange Online, que permite tamanhos de fotos de até 648 pixels por 648 pixels. Além disso, Exchange Server pode ressarcar automaticamente essas fotos para uso em diferentes produtos, conforme necessário. Normalmente, isso significa três tamanhos e resoluções de fotos diferentes:
  
- 64 pixels por 64 pixels, o tamanho usado para o atributo thumbnailPhoto do Active Directory. Se você carregar uma foto no Exchange Server, o Exchange criará automaticamente uma versão de 64 pixels por 64 pixels dessa foto e atualizará o atributo thumbnailPhoto do usuário. Observe, no entanto, que o inverso não é verdadeiro: se você atualizar manualmente o atributo thumbnailPhoto no Active Directory, a foto na caixa de correio do Exchange do usuário não será atualizada automaticamente.
    
- 96 pixels por 96 pixels, para uso no Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App e Skype for Business.
    
- 648 pixels por 648 pixels para uso no Skype for Business e Skype for Business Web App Skype for Business Web App.
    
> [!NOTE]
> Se você tiver os recursos, é recomendável carregar fotos 648 x 648; que fornece a resolução máxima e a qualidade de imagem ideal em qualquer um dos aplicativos do Office 2013. Cada foto JPEG com um tamanho de 648 x 648 e uma profundidade de 24 bits resulta em um tamanho de arquivo de aproximadamente 240 kilobytes. Isso significa que você precisará de aproximadamente 1 megabyte de espaço em disco para cada 4 fotos de usuário. 
  
As fotos de alta resolução, que são acessadas usando o Exchange Web Services, podem ser carregadas por usuários que executam o Outlook 2013 Web App; os usuários só têm permissão para atualizar suas próprias fotos. Os administradores, no entanto, podem atualizar a foto para qualquer usuário usando o Shell de Gerenciamento do Exchange e uma série de Windows PowerShell comandos semelhantes aos seguintes:
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

O primeiro comando no exemplo anterior usa o cmdlet para ler o conteúdo do arquivo C:\Photos\Kenmyer.jpg e armazenar esses dados em uma variável `Get-Content` chamada $photo. No segundo comando, o cmdlet do Exchange é usado para carregar a foto e anexar essa foto à `Set-UserPhoto` conta de usuário de Ken Myer.
  
> [!NOTE]
> Neste exemplo, o nome de exibição do Active Directory de Ken Myer é usado como a identidade da conta de usuário. Você também pode fazer referência a uma conta de usuário usando outros identificadores, como o endereço SMTP do usuário ou seu Nome de Entidade de Usuário. Consulte a documentação do cmdlet Set-UserPhoto para [https://go.microsoft.com/fwlink/p/?LinkId=268536](/powershell/module/exchange/set-userphoto) obter mais informações
  
Carregar a foto não equivale a atribuir essa foto à conta de usuário de Ken Myer. Em vez disso, carregar a foto simplesmente resulta em uma visualização dessa foto a ser exibida na página Opções do Outlook Web App. Para atribuir essa foto à conta de  usuário, o usuário deve clicar em Salvar na página Opções ou o administrador deve executar o terceiro comando no exemplo. Esse terceiro comando usa o parâmetro Save para atribuir a foto à conta de usuário de Ken Myer:
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Para verificar se a nova foto foi atribuída à conta de usuário, Ken Myer pode fazer logon no Skype for Business, selecione **Opções** e selecione **Minha Imagem**. A foto recém-carregada deve ser exibida como a foto pessoal de Ken. Como alternativa, os administradores podem verificar a foto de qualquer usuário iniciando o Internet Explorer e navegando para uma URL semelhante a esta:
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

Se o administrador puder exibir a foto usando o Internet Explorer, mas o usuário não puder exibir sua foto no Skype for Business, pode haver um problema de conectividade com os Serviços Web do Exchange ou com o serviço de descoberta automática do Exchange.
  
Observe também que nenhuma configuração adicional é necessária para disponibilizar essa foto no Skype for Business. Em vez disso, a foto estará disponível instantaneamente depois que ela tiver sido carregada e o `Set-UserPhoto` cmdlet tiver sido executado.