---
title: 'Lync Server 2013: Configurando o uso de fotos de alta resolução'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the use of high-resolution photos in Lync Server 2013
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49733753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7d73970bd30aa72294369eac1d8206d19664230
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41996446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a>Configurando o uso de fotos de alta resolução no Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-05_

O Microsoft Lync Server 2010 forneceu a capacidade de os usuários exibir fotos de seus contatos (e disponibilizar suas próprias fotos para outros). Normalmente, essas fotos foram armazenadas como parte do atributo thumbnailPhoto do usuário no Active Directory. Isso colocou uma séria limitação no tamanho e na resolução das fotos: o atributo thumbnailPhoto só pode conter uma fotografia com um tamanho máximo de 48 pixels por 48 pixels.

No Microsoft Lync Server 2013, no entanto, as fotos podem ser armazenadas em uma caixa de correio do Microsoft Exchange Server 2013 de um usuário; Isso permite tamanhos de fotos de até 648 pixels por 648 pixels. Além disso, o Exchange 2013 pode redimensionar automaticamente essas fotos para uso em diferentes produtos, conforme necessário. Normalmente, isso significa três tamanhos e resoluções de fotos diferentes:

  - 48 pixels por 48 pixels, o tamanho usado para o atributo thumbnailPhoto do Active Directory. Se você carregar uma foto para o Exchange 2013 o Exchange criará automaticamente um pixel de 48 por 48 pixel versão da foto e atualizará o atributo thumbnailPhoto do usuário. No entanto, observe que o inverso não é verdadeiro: se você atualizar manualmente o atributo thumbnailPhoto no Active Directory, a foto na caixa de correio do Exchange 2013 do usuário não será atualizada automaticamente.

  - 96 pixels por 96 pixels, para uso no Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App e Lync 2013.

  - 648 pixels por 648 pixels para uso no Lync 2013 e no Microsoft Lync Web App.

<div>


> [!NOTE]  
> Se você tiver os recursos, recomendamos carregar fotos do 648x648; Isso fornece a resolução máxima e a qualidade de imagem ideal em qualquer um dos aplicativos do Office 2013. Cada foto JPEG com um tamanho de 648x648 e uma profundidade de 24 bits resulta em um tamanho de arquivo de aproximadamente 240 kilobytes. Isso significa que você precisará de aproximadamente 1 megabyte de espaço em disco para cada 4 fotos do usuário.



</div>

Fotos de alta resolução, que são acessadas usando os serviços Web do Exchange, podem ser carregadas por usuários que estejam executando o Outlook 2013 Web App; os usuários só têm permissão para atualizar sua própria foto. No entanto, os administradores podem atualizar a foto de qualquer usuário usando o Shell de gerenciamento do Exchange e uma série de comandos do Windows PowerShell, semelhante à seguinte:

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

O primeiro comando no exemplo anterior usa o cmdlet Get-Content para ler o conteúdo do arquivo C:\\photos\\kenmyer. jpg e armazená-los em uma variável chamada $Photo. No segundo comando, o cmdlet do Exchange Set-UserPhoto é usado para carregar a foto e anexá-la à conta de usuário de Ken Myer.

<div>


> [!NOTE]  
> Neste exemplo, o nome de exibição do Active Directory de Ken Myer é usado como a identidade da conta de usuário. Você também pode fazer referência a uma conta de usuário usando outros identificadores, como o endereço SMTP do usuário ou seu nome de usuário principal. Consulte a documentação do cmdlet Set-UserPhoto em <A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A> para obter mais informações



</div>

Carregar a foto não é igual a atribuir essa foto à conta de usuário de Ken Myer. Em vez disso, carregar a foto simplesmente resulta em uma visualização dessa foto para ser exibida na página Opções do Outlook Web App. Para atribuir essa foto à conta de usuário, o usuário deve clicar em **salvar** na página opções ou o administrador deve executar o terceiro comando no exemplo. Esse terceiro comando usa o parâmetro Save para atribuir a foto à conta de usuário de Ken Myer:

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

Para verificar se a nova foto foi atribuída à conta de usuário, Ken Myer pode fazer logon no Lync 2013, selecionar **Opções**e selecionar **minha imagem**. A foto recém carregada deve ser exibida como foto pessoal de Ken. Como alternativa, os administradores podem verificar a foto de qualquer usuário, iniciando o Internet Explorer e navegando para uma URL semelhante a esta:

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

Se o administrador pode exibir a foto usando o Internet Explorer, mas o usuário não pode exibir sua foto no Lync 2013, que geralmente indica um problema de conectividade com os serviços Web do Exchange ou com o serviço de descoberta automática do Exchange.

Observe também que nenhuma configuração adicional é necessária para tornar essa foto disponível no Lync 2013. Em vez disso, a foto estará disponível instantaneamente depois de ser carregada e o cmdlet Set-UserPhoto tiver sido executado.

</div>

<span> </span>

</div>

</div>

</div>

