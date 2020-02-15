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

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a><span data-ttu-id="acea3-102">Configurando o uso de fotos de alta resolução no Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acea3-102">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acea3-103">_**Última modificação do tópico:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="acea3-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="acea3-104">O Microsoft Lync Server 2010 forneceu a capacidade de os usuários exibir fotos de seus contatos (e disponibilizar suas próprias fotos para outros).</span><span class="sxs-lookup"><span data-stu-id="acea3-104">Microsoft Lync Server 2010 provided the ability for users to view photos of their contacts (and to make their own photos available to others).</span></span> <span data-ttu-id="acea3-105">Normalmente, essas fotos foram armazenadas como parte do atributo thumbnailPhoto do usuário no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="acea3-105">Typically these photos were stored as part of the user's thumbnailPhoto attribute in Active Directory.</span></span> <span data-ttu-id="acea3-106">Isso colocou uma séria limitação no tamanho e na resolução das fotos: o atributo thumbnailPhoto só pode conter uma fotografia com um tamanho máximo de 48 pixels por 48 pixels.</span><span class="sxs-lookup"><span data-stu-id="acea3-106">That placed a serious limitation on the size and resolution of the photos: the thumbnailPhoto attribute can only hold a photograph with a maximum size of 48 pixels by 48 pixels.</span></span>

<span data-ttu-id="acea3-107">No Microsoft Lync Server 2013, no entanto, as fotos podem ser armazenadas em uma caixa de correio do Microsoft Exchange Server 2013 de um usuário; Isso permite tamanhos de fotos de até 648 pixels por 648 pixels.</span><span class="sxs-lookup"><span data-stu-id="acea3-107">In Microsoft Lync Server 2013, however, photos can be stored in a user's Microsoft Exchange Server 2013 mailbox; that allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="acea3-108">Além disso, o Exchange 2013 pode redimensionar automaticamente essas fotos para uso em diferentes produtos, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="acea3-108">In addition to that, Exchange 2013 can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="acea3-109">Normalmente, isso significa três tamanhos e resoluções de fotos diferentes:</span><span class="sxs-lookup"><span data-stu-id="acea3-109">Typically that means three different photo sizes and resolutions:</span></span>

  - <span data-ttu-id="acea3-110">48 pixels por 48 pixels, o tamanho usado para o atributo thumbnailPhoto do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="acea3-110">48 pixels by 48 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="acea3-111">Se você carregar uma foto para o Exchange 2013 o Exchange criará automaticamente um pixel de 48 por 48 pixel versão da foto e atualizará o atributo thumbnailPhoto do usuário.</span><span class="sxs-lookup"><span data-stu-id="acea3-111">If you upload a photo to Exchange 2013 Exchange will automatically create a 48 pixel by 48 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="acea3-112">No entanto, observe que o inverso não é verdadeiro: se você atualizar manualmente o atributo thumbnailPhoto no Active Directory, a foto na caixa de correio do Exchange 2013 do usuário não será atualizada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="acea3-112">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange 2013 mailbox will not automatically be updated.</span></span>

  - <span data-ttu-id="acea3-113">96 pixels por 96 pixels, para uso no Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App e Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="acea3-113">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App, and Lync 2013.</span></span>

  - <span data-ttu-id="acea3-114">648 pixels por 648 pixels para uso no Lync 2013 e no Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="acea3-114">648 pixels by 648 pixels for use in Lync 2013 and Microsoft Lync Web App.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="acea3-115">Se você tiver os recursos, recomendamos carregar fotos do 648x648; Isso fornece a resolução máxima e a qualidade de imagem ideal em qualquer um dos aplicativos do Office 2013.</span><span class="sxs-lookup"><span data-stu-id="acea3-115">If you have the resources, it is recommended that you upload 648x648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="acea3-116">Cada foto JPEG com um tamanho de 648x648 e uma profundidade de 24 bits resulta em um tamanho de arquivo de aproximadamente 240 kilobytes.</span><span class="sxs-lookup"><span data-stu-id="acea3-116">Each JPEG photo with a size of 648x648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="acea3-117">Isso significa que você precisará de aproximadamente 1 megabyte de espaço em disco para cada 4 fotos do usuário.</span><span class="sxs-lookup"><span data-stu-id="acea3-117">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span>



</div>

<span data-ttu-id="acea3-118">Fotos de alta resolução, que são acessadas usando os serviços Web do Exchange, podem ser carregadas por usuários que estejam executando o Outlook 2013 Web App; os usuários só têm permissão para atualizar sua própria foto.</span><span class="sxs-lookup"><span data-stu-id="acea3-118">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="acea3-119">No entanto, os administradores podem atualizar a foto de qualquer usuário usando o Shell de gerenciamento do Exchange e uma série de comandos do Windows PowerShell, semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="acea3-119">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="acea3-120">O primeiro comando no exemplo anterior usa o cmdlet Get-Content para ler o conteúdo do arquivo C:\\photos\\kenmyer. jpg e armazená-los em uma variável chamada $Photo.</span><span class="sxs-lookup"><span data-stu-id="acea3-120">The first command in the preceding example uses the Get-Content cmdlet to read the contents of the file C:\\Photos\\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="acea3-121">No segundo comando, o cmdlet do Exchange Set-UserPhoto é usado para carregar a foto e anexá-la à conta de usuário de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="acea3-121">In the second command, the Exchange cmdlet Set-UserPhoto is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="acea3-122">Neste exemplo, o nome de exibição do Active Directory de Ken Myer é usado como a identidade da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="acea3-122">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="acea3-123">Você também pode fazer referência a uma conta de usuário usando outros identificadores, como o endereço SMTP do usuário ou seu nome de usuário principal.</span><span class="sxs-lookup"><span data-stu-id="acea3-123">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="acea3-124">Consulte a documentação do cmdlet Set-UserPhoto em <A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A> para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="acea3-124">See the documentation for the Set-UserPhoto cmdlet at <A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A> for more information</span></span>



</div>

<span data-ttu-id="acea3-125">Carregar a foto não é igual a atribuir essa foto à conta de usuário de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="acea3-125">Uploading the photo does not equate to assigning that photo to Ken Myer's user account.</span></span> <span data-ttu-id="acea3-126">Em vez disso, carregar a foto simplesmente resulta em uma visualização dessa foto para ser exibida na página Opções do Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="acea3-126">Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page.</span></span> <span data-ttu-id="acea3-127">Para atribuir essa foto à conta de usuário, o usuário deve clicar em **salvar** na página opções ou o administrador deve executar o terceiro comando no exemplo.</span><span class="sxs-lookup"><span data-stu-id="acea3-127">To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example.</span></span> <span data-ttu-id="acea3-128">Esse terceiro comando usa o parâmetro Save para atribuir a foto à conta de usuário de Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="acea3-128">That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="acea3-129">Para verificar se a nova foto foi atribuída à conta de usuário, Ken Myer pode fazer logon no Lync 2013, selecionar **Opções**e selecionar **minha imagem**.</span><span class="sxs-lookup"><span data-stu-id="acea3-129">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Lync 2013, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="acea3-130">A foto recém carregada deve ser exibida como foto pessoal de Ken.</span><span class="sxs-lookup"><span data-stu-id="acea3-130">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="acea3-131">Como alternativa, os administradores podem verificar a foto de qualquer usuário, iniciando o Internet Explorer e navegando para uma URL semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="acea3-131">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

<span data-ttu-id="acea3-132">Se o administrador pode exibir a foto usando o Internet Explorer, mas o usuário não pode exibir sua foto no Lync 2013, que geralmente indica um problema de conectividade com os serviços Web do Exchange ou com o serviço de descoberta automática do Exchange.</span><span class="sxs-lookup"><span data-stu-id="acea3-132">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Lync 2013, that typically indicates a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>

<span data-ttu-id="acea3-133">Observe também que nenhuma configuração adicional é necessária para tornar essa foto disponível no Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="acea3-133">Note, too that no additional configuration is required in order to make this photo available in Lync 2013.</span></span> <span data-ttu-id="acea3-134">Em vez disso, a foto estará disponível instantaneamente depois de ser carregada e o cmdlet Set-UserPhoto tiver sido executado.</span><span class="sxs-lookup"><span data-stu-id="acea3-134">Instead, the photo will be instantly available after it has been uploaded and the Set-UserPhoto cmdlet has been run.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

